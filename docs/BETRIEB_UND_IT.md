# Betrieb und IT – Arbeitsgrundlage

**Status:** Interner Arbeitsentwurf · keine technische Freigabe der IT.

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
- Git für Konfigurationen, Skripte, QML, Vorlagen und Migrationen, nicht für produktive Geodaten oder Backups (A30).
- TEST und PROD trennen; einfache kontrollierte Releases statt vollständiger CI/CD-Pflicht (A27, A30).
- Zugang intern/VPN; externe authentifizierte Zusammenarbeit nur nach Bedarf. Serverrechte gelten unabhängig von der Oberfläche (A09, A18, A25, A26).

## A24 – Variantenvergleich für IT-Abstimmung (noch offen)

| Variante | Stärken | Risiken / Prüfbedarf |
|---|---|---|
| A – Native Dienste auf VMs | Bekannte Betriebsweise, direkte Diagnose | Konfigurationsdrift, aufwendigere reproduzierbare Installation |
| B – PostgreSQL nativ, GIS-Dienste containerisiert | Trennung persistenter DB und paketierter Dienste | Mischbetrieb, Update-/Backup-Schnittstellen |
| C – Weitgehend containerisiert | Reproduzierbare Services, standardisierte Bereitstellung | Kompetenzbedarf, persistente Daten, Orchestrierung nicht automatisch nötig |

**Bewertungskriterien:** IT-Kompetenz, Sicherheitsvorgaben, Wartbarkeit, Updatefähigkeit, Backup/Restore, Debugging, Ressourceneinsatz, langfristige Zukunftsfähigkeit. Keine Container-Orchestrierung ohne Bedarf. Entscheidung mit IT nach kleinem PoC und Betriebssicht.

## Noch abzustimmen

1. **Identität/SSO (A25):** bestehendes AD/M365, geeigneter OIDC/OAuth2-IdP, QGIS Desktop, externe Personen und mobile Geräte.
2. **Rechte (A26):** Fachrollen, AD-Gruppen, DB-/Service-/Extract-/Mobile-Durchsetzung und Testfälle.
3. **Backup (A28):** konsistente PostgreSQL-Sicherung, Dateien/QGIS-Ressourcen, Restore-Proben, RPO/RTO und mobile unsynchronisierte Daten.
4. **Monitoring (A29):** DB, funktionaler WMS-Aufruf, Webviewer, Authentifizierung, Extract, Backup, datenschutzgerechte Logs.
5. **Betriebsorganisation (A31):** Installation, Patchmanagement, DB-Migrationen, Vorfälle, Vertretung.
6. **Wissensaufbau (A33):** Schulungen und Einarbeitung passend zu Rollen; Zeit-/Personal-/Budgetbedarf sichtbar machen.

## Mindestabnahme vor produktivem Pilot

Zugriffsrechte und Datenintegrität getestet, Backup/Restore nachgewiesen, dokumentierter Update-/Rollback-Weg, grundlegende Funktionsüberwachung, zuständige Ansprechpartner und fachlich abgenommener Pilotablauf. Die konkrete Ausgestaltung mit IT festlegen.
