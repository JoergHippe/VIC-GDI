# IT-Briefing – [GDI](ANHANG_A_GLOSSAR.md#gdi), Infrastruktur und Betrieb

**Status:** Interner Arbeitsentwurf · keine technische Freigabe der IT.

## Worum es geht

Ein [GIS](ANHANG_A_GLOSSAR.md#gis) bearbeitet und zeigt räumliche Daten, etwa den dokumentierten Verlauf einer Leitung. Die GDI organisiert, wo solche Daten geführt werden, wie berechtigte Personen sie finden und nutzen und wer sie pflegt. Die Baubetreuung kann beispielsweise einen Leitungsverlauf fachlich prüfen und übernehmen. Berechtigte Planende können anschließend denselben freigegebenen Stand in [QGIS](ANHANG_A_GLOSSAR.md#qgis) nutzen.

**Gesprächsziel:** Machbaren Betriebsrahmen, Zuständigkeiten und Aufwand für die nächste Planungsstufe ermitteln. Der Termin dient der Abstimmung. Technische Erprobungen und Bereitstellung folgen erst nach gesonderter Planung.

Die [Architekturübersicht](03_ARCHITEKTUR.md#architekturübersicht-logisches-zielbild) zeigt, wie Desktop, Browser und Mobilgeräte auf Daten und Dienste zugreifen.

## Mindestbedarf für einen produktiven Pilotbetrieb

| Bereich | Was IT bereitstellen oder verbindlich klären soll |
|---|---|
| Hosting und Speicher | Verwaltete Serverumgebung mit getrennten TEST-/PROD-Umgebungen, persistentem Speicher und freigegebenen Dateiablagen. Dimensionierung anhand von Datenvolumen, Wachstum, gleichzeitigen Nutzern, Kartenlast und Sicherungsbedarf ableiten. |
| Datenbank | Betreibbare [PostgreSQL](ANHANG_A_GLOSSAR.md#postgresql)-Instanz mit [PostGIS](ANHANG_A_GLOSSAR.md#postgis) für geeignete gemeinsam genutzte Geodaten. Rollen, Verbindungsschutz, Updates und Sicherung mit GIS abstimmen. |
| Kartendienste | Wenn Webkarten im Pilotumfang liegen, internen HTTPS-Endpunkt und den Betrieb eines Kartendiensts einplanen. [QGIS Server](ANHANG_A_GLOSSAR.md#qgis-server) ist der bevorzugte Kandidat und stellt Karten aus freigegebenen Webprojekten bereit. QGIS Desktop greift je nach Quelle direkt auf Datenbank, Dateien oder Dienste zu. |
| Netz und Zugang | Interne Namensauflösung, Zertifikate, Firewallregeln und Zugriff vom Arbeitsplatz bzw. über [VPN](ANHANG_A_GLOSSAR.md#vpn) klären. Datenbankzugriff auf erforderliche Clients und Dienste begrenzen. |
| Identitäten und Rechte | Vorhandene Unternehmensidentitäten prüfen. [AD DS](ANHANG_A_GLOSSAR.md#ad) und [Microsoft Entra ID](ANHANG_A_GLOSSAR.md#entra-id) unterscheiden. Anmeldung und Rechte für Browser, Desktop-Datenbankzugriff und technische Dienstkonten separat festlegen. GIS und Fachbereiche definieren Lesende, Bearbeitende und Freigabeberechtigte. |
| Sicherung und Betrieb | Datenbankkonsistente Sicherung einschließlich benötigter Rollen, Projektdateien, abhängiger Ressourcen und Konfigurationen. Wiederherstellung in TEST, Überwachung, Patchfenster, Support und Vertretung einplanen. Zielwerte für Datenverlust und Wiederanlauf gemeinsam festlegen. |

**Im Konzept geklärt:** Die gemeinsame Datenbasis in PostGIS und die beiden Pilotbereiche sind festgelegt. On-prem/[Proxmox](ANHANG_A_GLOSSAR.md#proxmox), QGIS Server und zentrale Unternehmensidentitäten sind bevorzugte Richtungen. Die technische Freigabe und konkrete Ausgestaltung stehen aus.

**Bedarfsabhängig:** Externe Zugänge, mobile Cloud-Anbindung, weitgehende Automatisierung und [Hochverfügbarkeit](ANHANG_A_GLOSSAR.md#ha) erst anhand der bestätigten Pilotabläufe und Betriebsziele bewerten. Der erweiterte Katalog und die zentrale Projektablage stehen unter [Prüfvorbehalt](04_ENTSCHEIDUNGEN.md#erneute-prüfung-a04-a15-und-a36).

## Rollen und Verantwortlichkeiten ([A31](04_ENTSCHEIDUNGEN.md#a31))

| Aufgabenbereich | Vorläufige Federführung |
|---|---|
| Fachliche Anforderungen, Geodatenmodelle, QGIS-Ressourcen | GIS-Team |
| Fachliche Qualität und Pflege der Fachdaten | Zuständiger Fachbereich |
| Server, VMs, Netzwerk, VPN, Basis-IT-Sicherheit | IT |
| AD/Identitäten und zentrale Authentifizierung | IT |
| Backups, Monitoring und Wiederherstellbarkeit | IT mit GIS-spezifischen Anforderungen |
| PostgreSQL-Administration, GIS-Dienste, Updates | Gemeinsam; Federführung noch festzulegen |
| Berechtigungen | Fachliche Vorgaben GIS/Fachbereiche, technische Umsetzung mit IT |
| Support | GIS-Fachfragen GIS-Team; Infrastrukturstörungen IT |

Für kritische Aufgaben federführende Person und Vertretung festlegen; kein eigenes ITSM-System einführen ([A31](04_ENTSCHEIDUNGEN.md#a31), [A32](04_ENTSCHEIDUNGEN.md#a32)).

## Technische Rahmenbedingungen

- Bevorzugt On-prem auf vorhandener Proxmox-Infrastruktur, Linux/[Debian](ANHANG_A_GLOSSAR.md#debian) als naheliegende Option; keine endgültige VM-/Containerentscheidung ([A23](04_ENTSCHEIDUNGEN.md#a23), [A24](04_ENTSCHEIDUNGEN.md#a24)).
- Zentrale PostgreSQL/PostGIS-Datenhaltung mit fachlichen Schemas ([A02](04_ENTSCHEIDUNGEN.md#a02)).
- QGIS Server bevorzugt, technische Validierung erforderlich ([A10](04_ENTSCHEIDUNGEN.md#a10)).
- [Git](ANHANG_A_GLOSSAR.md#git) für Konfigurationen, Skripte, [QML](ANHANG_A_GLOSSAR.md#qml), Vorlagen und Migrationen, nicht für produktive Geodaten oder Backups ([A30](04_ENTSCHEIDUNGEN.md#a30)).
- TEST und PROD trennen; einfache kontrollierte Releases statt vollständiger [CI/CD](ANHANG_A_GLOSSAR.md#ci-cd)-Pflicht ([A27](04_ENTSCHEIDUNGEN.md#a27), [A30](04_ENTSCHEIDUNGEN.md#a30)).
- Zugang intern/VPN; externe authentifizierte Zusammenarbeit nur nach Bedarf. Serverrechte gelten unabhängig von der Oberfläche ([A09](04_ENTSCHEIDUNGEN.md#a09), [A18](04_ENTSCHEIDUNGEN.md#a18), [A25](04_ENTSCHEIDUNGEN.md#a25), [A26](04_ENTSCHEIDUNGEN.md#a26)).

## Serverbetriebssystem und Deployment ([A23](04_ENTSCHEIDUNGEN.md#a23)/[A24](04_ENTSCHEIDUNGEN.md#a24))

Windows bleibt der Ausgangspunkt für die vorhandenen Arbeitsplätze und Unternehmensdienste. Für die Server ist eine betreute Linux-VM (Debian als Kandidat) zu prüfen. Wenn Linux-Patching, Diagnose oder Vertretung intern schwierig sind, Aufwand für Qualifizierung oder externe Unterstützung ermitteln und mit einer Windows-Server-Variante vergleichen. Für Windows die Unterstützung der konkret benötigten Komponenten, Versionen, Erweiterungen und Betriebswerkzeuge klären.

VM und [Docker](ANHANG_A_GLOSSAR.md#docker) liegen auf unterschiedlichen Ebenen. Eine VM stellt das Betriebssystem bereit. Docker kann innerhalb einer geeigneten VM Dienste paketieren. IT bewertet Betriebssystem und Dienstbereitstellung getrennt.

| Variante | Stärken | Risiken / Prüfbedarf |
|---|---|---|
| A – Native Dienste auf VMs | Bekannte Betriebsweise, direkte Diagnose | Konfigurationsdrift, aufwendigere reproduzierbare Installation |
| B – PostgreSQL nativ, GIS-Dienste containerisiert | Trennung persistenter DB und paketierter Dienste | Mischbetrieb, Update-/Backup-Schnittstellen |
| C – Weitgehend containerisiert | Reproduzierbare Services, standardisierte Bereitstellung | Kompetenzbedarf, persistente Daten, Orchestrierung nicht automatisch nötig |

**Bewertungskriterien:** IT-Kompetenz, Sicherheitsvorgaben, Wartbarkeit, Updatefähigkeit, Backup/Restore, Debugging, Ressourceneinsatz, langfristige Zukunftsfähigkeit. Keine Container-Orchestrierung ohne Bedarf. Mit IT die dauerhaft betreibbaren Varianten eingrenzen. Verbleibende Machbarkeitsfragen bei Bedarf nach gesonderter Freigabe mit einem kleinen [PoC](ANHANG_A_GLOSSAR.md#poc) klären.

## Noch abzustimmen

1. **Identität/[SSO](ANHANG_A_GLOSSAR.md#sso) ([A25](04_ENTSCHEIDUNGEN.md#a25)):** Vorhandene Identitätsdienste und Gruppen prüfen. Für Browseranmeldung Eignung von [OIDC](ANHANG_A_GLOSSAR.md#oidc) klären, für Desktop den Datenbankzugriff separat betrachten. Externe Personen und mobile Geräte nach Bedarf einbeziehen.
2. **Rechte ([A26](04_ENTSCHEIDUNGEN.md#a26)):** Fachrollen und Gruppen den genutzten Zugriffspfaden zuordnen. Berechtigte und abgewiesene Zugriffe prüfen, bei Webkarten auch den direkten Dienstaufruf.
3. **Backup ([A28](04_ENTSCHEIDUNGEN.md#a28)):** konsistente PostgreSQL-Sicherung, Dateien/QGIS-Ressourcen, Restore-Proben, [RPO/RTO](ANHANG_A_GLOSSAR.md#rpo-rto) und mobile unsynchronisierte Daten.
4. **Monitoring ([A29](04_ENTSCHEIDUNGEN.md#a29)):** Vorhandene IT-Überwachung für Datenbank und Sicherung nutzen. Für tatsächlich eingesetzte GIS-Dienste Funktionsprüfungen ergänzen, etwa einen [WMS](ANHANG_A_GLOSSAR.md#wms)-Kartenaufruf. Alarmierung und datenschutzgerechte Protokollierung abstimmen.
5. **Betriebsorganisation ([A31](04_ENTSCHEIDUNGEN.md#a31)):** Installation, Patchmanagement, DB-Migrationen, Vorfälle, Vertretung.
6. **Wissensaufbau ([A33](04_ENTSCHEIDUNGEN.md#a33)):** Schulungen und Einarbeitung passend zu Rollen; Zeit-/Personal-/Budgetbedarf sichtbar machen.

## Agenda und Fragen für den IT-Termin (Vorschlag, 60 Minuten)

| Zeit | Gesprächspunkt und Leitfragen |
|---|---|
| 10 Min. | Zielbild und Pilotabläufe. Welche Nutzungspfade und Datenarten muss IT für die Aufwandsschätzung kennen? |
| 15 Min. | Hosting. Welche VM-, Linux- und Docker-Betriebsstandards gibt es? Welche Varianten kann IT dauerhaft betreuen und vertreten? Welche Last- und Speicherangaben fehlen? |
| 15 Min. | Zugriff. Welche AD-/M365-Integration und welche internen Netz- und VPN-Wege sind möglich? Wer verwaltet Gruppen, Zertifikate, Firewallregeln und Dienstkonten? |
| 15 Min. | Betrieb. Wer übernimmt PostgreSQL/PostGIS, GIS-Dienste, Updates und Störungen? Was decken vorhandene Sicherung und Überwachung ab? Wer koordiniert Wiederherstellung und Abnahme? |
| 5 Min. | Ergebnis festhalten. Pro offener Frage zuständige Person, benötigte Zuarbeit und Termin vereinbaren. Voraussetzungen und Aufwand für die nächste Freigabe benennen. |

### Ergebnis festhalten

| Frage | Ergebnis | Zuständige Person | Nächster Schritt | Termin |
|---|---|---|---|---|
| | | | | |

Technische Referenzen für die spätere Planung sind das [QGIS-Server-Handbuch](https://docs.qgis.org/3.44/pdf/en/QGIS-3.44-ServerUserGuide-en.pdf) und die [PostgreSQL-Dokumentation zu Sicherung und Wiederherstellung](https://www.postgresql.org/docs/current/backup.html).

## Mindestabnahme vor produktivem Pilot

Zugriffsrechte und Datenintegrität getestet, Backup/Restore nachgewiesen, dokumentierter Update-/Rollback-Weg, grundlegende Funktionsüberwachung, zuständige Ansprechpartner und fachlich abgenommener Pilotablauf. Die konkrete Ausgestaltung mit IT festlegen.
