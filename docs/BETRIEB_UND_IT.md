# IT-Briefing – GDI, Infrastruktur und Betrieb

**Status:** Interner Arbeitsentwurf · keine technische Freigabe der IT.

## Worum es geht

Ein [GIS](GLOSSAR.md#gis) bearbeitet und zeigt räumliche Daten, etwa den dokumentierten Verlauf einer Leitung. Die [GDI](GLOSSAR.md#gdi) organisiert, wo solche Daten geführt werden, wie berechtigte Personen sie finden und nutzen und wer sie pflegt. Die Baubetreuung kann beispielsweise einen Leitungsverlauf fachlich prüfen und übernehmen. Berechtigte Planende können anschließend denselben freigegebenen Stand in [QGIS](GLOSSAR.md#qgis) nutzen.

**Gesprächsziel:** Machbaren Betriebsrahmen, Zuständigkeiten und Aufwand für die nächste Planungsstufe ermitteln. Der Termin dient der Abstimmung. Technische Erprobungen und Bereitstellung folgen erst nach gesonderter Planung.

## Mindestbedarf für einen produktiven Pilotbetrieb

| Bereich | Was IT bereitstellen oder verbindlich klären soll |
|---|---|
| Hosting und Speicher | Verwaltete Serverumgebung mit getrennten TEST-/PROD-Umgebungen, persistentem Speicher und freigegebenen Dateiablagen. Dimensionierung anhand von Datenvolumen, Wachstum, gleichzeitigen Nutzern, Kartenlast und Sicherungsbedarf ableiten. |
| Datenbank | Betreibbare [PostgreSQL](GLOSSAR.md#postgresql)-Instanz mit [PostGIS](GLOSSAR.md#postgis) für geeignete gemeinsam genutzte Geodaten. Rollen, Verbindungsschutz, Updates und Sicherung mit GIS abstimmen. |
| Kartendienste | Wenn Webkarten im Pilotumfang liegen, internen HTTPS-Endpunkt und den Betrieb eines Kartendiensts einplanen. QGIS Server ist der bevorzugte Kandidat und stellt Karten aus freigegebenen Webprojekten bereit. QGIS Desktop greift je nach Quelle direkt auf Datenbank, Dateien oder Dienste zu. |
| Netz und Zugang | Interne Namensauflösung, Zertifikate, Firewallregeln und Zugriff vom Arbeitsplatz bzw. über [VPN](GLOSSAR.md#vpn) klären. Datenbankzugriff auf erforderliche Clients und Dienste begrenzen. |
| Identitäten und Rechte | [AD](GLOSSAR.md#ad)/M365 als Ausgangspunkt für zentrale Identitäten prüfen. Anmeldung und Rechte für Browser, Desktop-Datenbankzugriff und technische Dienstkonten separat festlegen. GIS und Fachbereiche definieren Lesende, Bearbeitende und Freigabeberechtigte. |
| Sicherung und Betrieb | Datenbankkonsistente Sicherung einschließlich benötigter Rollen, Projektdateien, abhängiger Ressourcen und Konfigurationen. Wiederherstellung in TEST, Überwachung, Patchfenster, Support und Vertretung einplanen. Zielwerte für Datenverlust und Wiederanlauf gemeinsam festlegen. |

**Im Konzept geklärt:** Die gemeinsame Datenbasis in PostGIS und die beiden Pilotbereiche sind festgelegt. On-prem/Proxmox, QGIS Server und zentrale Unternehmensidentitäten sind bevorzugte Richtungen. Die technische Freigabe und konkrete Ausgestaltung stehen aus.

**Bedarfsabhängig:** Externe Zugänge, mobile Cloud-Anbindung, weitgehende Automatisierung und Hochverfügbarkeit erst anhand der bestätigten Pilotabläufe und Betriebsziele bewerten. Der erweiterte Katalog und die zentrale Projektablage stehen unter [Prüfvorbehalt](ENTSCHEIDUNGEN.md#erneute-prüfung-a04-a15-und-a36).

## Rollen und Verantwortlichkeiten (A31)

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

Für kritische Aufgaben federführende Person und Vertretung festlegen; kein eigenes ITSM-System einführen (A31, A32).

## Technische Rahmenbedingungen

- Bevorzugt On-prem auf vorhandener Proxmox-Infrastruktur, Linux/Debian als naheliegende Option; keine endgültige VM-/Containerentscheidung (A23, A24).
- Zentrale PostgreSQL/PostGIS-Datenhaltung mit fachlichen Schemas (A02).
- QGIS Server bevorzugt, technische Validierung erforderlich (A10).
- [Git](GLOSSAR.md#git) für Konfigurationen, Skripte, QML, Vorlagen und Migrationen, nicht für produktive Geodaten oder Backups (A30).
- TEST und PROD trennen; einfache kontrollierte Releases statt vollständiger CI/CD-Pflicht (A27, A30).
- Zugang intern/VPN; externe authentifizierte Zusammenarbeit nur nach Bedarf. Serverrechte gelten unabhängig von der Oberfläche (A09, A18, A25, A26).

## Serverbetriebssystem und Deployment (A23/A24)

Windows bleibt der Ausgangspunkt für die vorhandenen Arbeitsplätze und Unternehmensdienste. Für die Server ist eine betreute Linux-VM (Debian als Kandidat) zu prüfen. Wenn Linux-Patching, Diagnose oder Vertretung intern schwierig sind, Aufwand für Qualifizierung oder externe Unterstützung ermitteln und mit einer Windows-Server-Variante vergleichen. Für Windows die Unterstützung der konkret benötigten Komponenten, Versionen, Erweiterungen und Betriebswerkzeuge klären.

VM und Docker liegen auf unterschiedlichen Ebenen. Eine VM stellt das Betriebssystem bereit. Docker kann innerhalb einer geeigneten VM Dienste paketieren. IT bewertet Betriebssystem und Dienstbereitstellung getrennt.

| Variante | Stärken | Risiken / Prüfbedarf |
|---|---|---|
| A – Native Dienste auf VMs | Bekannte Betriebsweise, direkte Diagnose | Konfigurationsdrift, aufwendigere reproduzierbare Installation |
| B – PostgreSQL nativ, GIS-Dienste containerisiert | Trennung persistenter DB und paketierter Dienste | Mischbetrieb, Update-/Backup-Schnittstellen |
| C – Weitgehend containerisiert | Reproduzierbare Services, standardisierte Bereitstellung | Kompetenzbedarf, persistente Daten, Orchestrierung nicht automatisch nötig |

**Bewertungskriterien:** IT-Kompetenz, Sicherheitsvorgaben, Wartbarkeit, Updatefähigkeit, Backup/Restore, Debugging, Ressourceneinsatz, langfristige Zukunftsfähigkeit. Keine Container-Orchestrierung ohne Bedarf. Entscheidung mit IT nach kleinem [PoC](GLOSSAR.md#poc) und Betriebssicht.

## Noch abzustimmen

1. **Identität/[SSO](GLOSSAR.md#sso) (A25):** bestehendes AD/M365, geeigneter OIDC/OAuth2-[IdP](GLOSSAR.md#idp), QGIS Desktop, externe Personen und mobile Geräte.
2. **Rechte (A26):** Fachrollen, AD-Gruppen, DB-/Service-/Extract-/Mobile-Durchsetzung und Testfälle.
3. **Backup (A28):** konsistente PostgreSQL-Sicherung, Dateien/QGIS-Ressourcen, Restore-Proben, [RPO/RTO](GLOSSAR.md#rpo-rto) und mobile unsynchronisierte Daten.
4. **Monitoring (A29):** DB, funktionaler WMS-Aufruf, Webviewer, Authentifizierung, Extract, Backup, datenschutzgerechte Logs.
5. **Betriebsorganisation (A31):** Installation, Patchmanagement, DB-Migrationen, Vorfälle, Vertretung.
6. **Wissensaufbau (A33):** Schulungen und Einarbeitung passend zu Rollen; Zeit-/Personal-/Budgetbedarf sichtbar machen.

## Agenda und Fragen für den IT-Termin (Vorschlag, 60 Minuten)

| Zeit | Gesprächspunkt und Leitfragen |
|---|---|
| 10 Min. | Zielbild und Pilotabläufe. Welche Nutzungspfade und Datenarten muss IT für die Aufwandsschätzung kennen? |
| 15 Min. | Hosting. Welche VM-, Linux- und Docker-Betriebsstandards gibt es? Welche Varianten kann IT dauerhaft betreuen und vertreten? Welche Last- und Speicherangaben fehlen? |
| 15 Min. | Zugriff. Welche AD-/M365-Integration und welche internen Netz- und VPN-Wege sind möglich? Wer verwaltet Gruppen, Zertifikate, Firewallregeln und Dienstkonten? |
| 15 Min. | Betrieb. Wer übernimmt PostgreSQL/PostGIS, GIS-Dienste, Updates und Störungen? Was decken vorhandene Sicherung und Überwachung ab? Wer koordiniert Wiederherstellung und Abnahme? |
| 5 Min. | Ergebnis festhalten. Pro offener Frage zuständige Person, benötigte Zuarbeit und Termin vereinbaren. Voraussetzungen und Aufwand für die nächste Freigabe benennen. |

Technische Referenzen für die spätere Planung sind das [QGIS-Server-Handbuch](https://docs.qgis.org/3.44/pdf/en/QGIS-3.44-ServerUserGuide-en.pdf) und die [PostgreSQL-Dokumentation zu Sicherung und Wiederherstellung](https://www.postgresql.org/docs/current/backup.html).

## Mindestabnahme vor produktivem Pilot

Zugriffsrechte und Datenintegrität getestet, Backup/Restore nachgewiesen, dokumentierter Update-/Rollback-Weg, grundlegende Funktionsüberwachung, zuständige Ansprechpartner und fachlich abgenommener Pilotablauf. Die konkrete Ausgestaltung mit IT festlegen.
