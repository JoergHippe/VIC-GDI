# Architekturentscheidungen A01–A38

**Status:** Konsolidierter interner Arbeitsentwurf. Dieses Register ist die führende Stelle für Beschlussstatus und Entscheidungsbegründungen. Die knappen Zusammenfassungen ersetzen nicht die spätere Detailprüfung mit IT und Fachbereichen.

**Quellenlage:** Erstkonsolidierung aus den bisherigen Architekturgesprächen A01–A38. Wo kein detailliertes Entscheidungsprotokoll vorliegt, sind die Aussagen bewusst auf die gesicherten Grundsätze begrenzt. Die Dokumente sind keine Implementierungs- oder Freigabenachweise.

**Statusschlüssel:** **B** = beschlossen; **G** = Grundsatz beschlossen, Detail offen; **Z** = zurückgestellt; **O** = offen.

| ID | Thema | Status | Festlegung / Ergebnis |
|---|---|---|---|
| A01 | Ausrichtung | B | Fachbereichsneutrale GDI, Piloten BB und Verkehrsanlagenplanung |
| A02 | Datenbankorganisation | B | Gemeinsame [PostGIS](GLOSSAR.md#postgis)-Datenbank mit fachlichen Schemas |
| A03 | Projektbezug | B | Fachliche gemeinsame Tabellen; `project_id` selektiv, Ausnahmen zulässig |
| A04 | [QGIS](GLOSSAR.md#qgis)-Projekte | B | Zentrale Ressourcen, eigenständige Fach-QGIS-Projekte; getrennte Webprojekte · [überprüfungsbedürftig](#erneute-prüfung-a04-a15-und-a36) |
| A05 | Externe Basisdaten | B | Live bevorzugt; unveränderliche, nachvollziehbare Snapshots bei Bedarf |
| A06 | Projektgeometrie | B | Optional; keine verpflichtende Projekt-AOI |
| A07 | Projektstammdaten | B | Schlanker gemeinsamer Kern, kein Projektmanagement |
| A08 | Fachbereichsübergreifende Nutzung | B | Gemeinsame Projektidentität, eindeutige Datenhoheit, keine führenden Dubletten |
| A09 | Datenzugriff | B | Freigegebene gemeinsame Daten lesbar, Schreiben zuständigkeitsabhängig; serverseitige Durchsetzung |
| A10 | GIS-Server | G | QGIS Server bevorzugt; [PoC](GLOSSAR.md#poc) und OGC-Fähigkeiten prüfen |
| A11 | Webviewer | B | Etablierte Open-Source-Lösung, gezielte Erweiterungen statt Eigenportal |
| A12 | Geodatenauszug | G | Schlanker Extract-Service mit Rechteprüfung; Clipping/Selektion per PoC klären |
| A13 | Mobile Arbeit | G | QField/Happy Mini Q, etablierte Synchronisation, keine Eigenentwicklung |
| A14 | [ETL](GLOSSAR.md#etl) | B | Stufenweise Skript-/Importautomatisierung, keine ETL-Plattform vorab |
| A15 | Metadaten | B | Schlanker quellen-/datensatz-/dienstbezogener Katalog · [überprüfungsbedürftig](#erneute-prüfung-a04-a15-und-a36) |
| A16 | Datenqualität | B | Amtliche Daten technisch prüfen, eigene Daten pragmatisch fachlich prüfen; kein formales QA-System |
| A17 | QGIS-Stile | B | Zentrale [Git](GLOSSAR.md#git)-versionierte QML, projektspezifische Overrides |
| A18 | Webpublikation | B | Eigene Webkartenprojekte; primär intern, extern geschützt bei Bedarf |
| A19 | Web-UI | B | Eine Anwendung, einfache Grundansicht und bedarfsbezogene Erweiterungen |
| A20 | Suche | B | Schlanke integrierte Suche; keine separate Suchplattform |
| A21 | Koordinatenreferenz | B | EPSG:25832/25833 bevorzugt; Ausnahmen und Höhenbezug beachten |
| A22 | Raster | B | Externe Dienste bevorzugt, lokale GeoTIFF/COG nach Bedarf |
| A23 | Hosting | G | On-prem/Proxmox bevorzugt; hybride Optionen möglich |
| A24 | Deployment | O | VM-nativ, hybrid oder containerisiert – gemeinsam mit IT entscheiden |
| A25 | Identitäten | G | AD/M365 und zentraler IdP bevorzugt; technische Umsetzung IT-Entscheid |
| A26 | Berechtigungen | G | Gemeinsames Rollen-/Rechteprinzip; Durchsetzung über alle Zugriffspfade, IT-Detailklärung |
| A27 | Umgebungen | G | Schlanke getrennte TEST/PROD, lokale Entwicklung, Git/Migrationen; IT-Abstimmung |
| A28 | Backup | G | Bestehendes IT-Backup plus GDI-spezifische Sicherung/Restore; IT-Abstimmung |
| A29 | Monitoring | G | Bestehendes Monitoring um funktionale GIS-Prüfungen ergänzen; IT-Abstimmung |
| A30 | Deploymentprozess | G | Git für geeignete Ressourcen, zunächst kontrollierte Bereitstellung, später bedarfsweise automatisieren; IT-Abstimmung |
| A31 | Betriebsverantwortung | G | Gemeinsames GIS-/IT-Betriebsmodell, konkrete Zuständigkeiten noch abzustimmen |
| A32 | Support und Weiterentwicklung | B | Schlanker gemeinsamer Prozess, vorhandene Werkzeuge bevorzugen |
| A33 | Wissensaufbau | B | Themen-/rollenbezogen A/B/C kombinieren; Ressourcen verbindlich einplanen |
| A34 | Pilotstrategie | B | Gemeinsame Basis, zwei früh beteiligte und zeitlich staffelbare Piloten |
| A35 | [MVP](GLOSSAR.md#mvp) | B | Priorisierter anpassbarer Umfang; gemeinsame Basis und Pilot-MVPs unterscheiden |
| A36 | Migration | B | **B+**: verbindliche Zielarchitektur, selektive Migration, problematische SharePoint-/OneDrive-GIS-Arbeitsbestände ablösen · [überprüfungsbedürftig](#erneute-prüfung-a04-a15-und-a36) |
| A37 | Datenlebenszyklus | Z | Option B plausibel, aber nicht beschlossen; später klären |
| A38 | Datenbankregeln | Z | Option B plausibel, aber nicht beschlossen; später klären |

## Erneute Prüfung A04, A15 und A36

Die Kennzeichnung ergänzt den bisherigen Status. Bis zu einer dokumentierten Folgeentscheidung gelten die bisherigen Festlegungen.

| Bezug | Neue Präferenz zur Prüfung | Vor einer Änderung klären |
|---|---|---|
| A04 | QGIS-Projekte zentral in PostgreSQL ablegen. Fachprojekte und getrennte Webprojekte bleiben der Ausgangspunkt. | Umfang, Projekt- und Publikationsrechte, parallele Bearbeitung, Versionierung, externe Ressourcen und Wiederherstellung. QGIS unterstützt Projektablage in PostgreSQL. [QGIS-Dokumentation](https://docs.qgis.org/testing/en/docs/user_manual/introduction/project_files.html#managing-qgis-project-files-from-postgresql-databases) |
| A15 | Internen Katalog über den bisherigen schlanken Umfang hinaus erweitern und Metadaten hybrid pflegen. | Welche Suche und Felder bringen Nutzen? Technisch ableitbare Angaben wie Schema oder Importzeit automatisiert übernehmen. Fachliche Angaben wie Zweck, Zuständigkeit und Nutzungsauflagen redaktionell pflegen und freigeben. Führende Quelle je Feld und Aktualisierung bei Konflikten klären. |
| A36 | Zentrale PostgreSQL-Projektablage als Ziel für geeignete Projekte prüfen. | Projektinventar, Pfade und externe Dateien, Rechte, Übernahme, Rückfallweg und fachliche Abnahme. Selektive Migration und kontrollierte Ablösung problematischer Synchronisationsordner bleiben der Ausgangspunkt. |

### Prüfrahmen für die Projektablage (A04/A36)

Für eine spätere, gesondert freigegebene Erprobung genügt ein repräsentatives Projekt mit PostGIS-Vektordaten und einer referenzierten Rasterdatei, zwei QGIS-Arbeitsplätzen und getrennten Rollen.

- **Grundfunktion:** Projekt speichern und mit dem zweiten Konto öffnen. Leserecht, verweigertes Überschreiben und erreichbare Rasterreferenzen prüfen.
- **Zusammenarbeit:** Gleichzeitige Änderungen an Vektordaten und konkurrierende Änderungen an der Projektdefinition getrennt betrachten. Das Konfliktverhalten muss nachvollziehbar sein. Für Datenänderungen ist ein Umgang ohne unkontrollierten Verlust erforderlich.
- **Wiederherstellung:** Einen praktikablen Weg zu einem früheren Projektstand samt benötigten Ressourcen prüfen.
- **Webpublikation:** Bei vorgesehener Webnutzung zusätzlich Kartenbereitstellung über QGIS Server mit den vorgesehenen Rechten prüfen. Die Desktop-Eignung separat bewerten.

### Katalogumfang und Standards (A15)

Priorisierte Suchfälle und vorhandene Quellen bestimmen den Katalogumfang. [OGC API – Records](https://docs.ogc.org/is/20-004r1/20-004r1.html) kann als Referenz für die Auffindbarkeit dienen. Eine Katalogsoftware oder Schnittstelle wird erst bei konkretem Bedarf ausgewählt.

## Erläuterungen zu entscheidenden Festlegungen

### A09 / A26 – Datenhoheit und Rechte
Eine fachlich führende Stelle je gemeinsamem Datenbestand. Lesende fachbereichsübergreifende Nutzung nach Freigabe, Schreibrechte nach Rolle und Zuständigkeit. Die Durchsetzung muss in DB, Diensten, Extract und mobilen Pfaden wirksam sein; das konkrete Berechtigungsdesign ist offen.

### A12 – Extract
Geplante Formate GPKG, Shapefile, GeoJSON und CSV; Flächenauswahl aus Karte, GeoJSON/Shapefile oder BBox und optional Ziel-[CRS](GLOSSAR.md#crs). **Selektion ganzer Objekte ist nicht gleich geometrischem Zuschnitt.** Diese Unterscheidung ist vor Implementierung zu erproben.

### A24 – Deployment
Die Varianten **A native VMs**, **B Datenbank nativ plus containerisierte GIS-Dienste**, **C umfassende Containerisierung** bleiben gleichberechtigte Untersuchungsoptionen. Vergleich nach Betrieb, IT-Know-how, Sicherheit, Wartbarkeit, Backup, Kosten und Zukunftsfähigkeit; kein voreiliger Technologieentscheid.

### A33 – Wissensaufbau
Eigenständige Einarbeitung, gezielte Schulungen und umfangreiche Schulung/Zertifizierung können je Thema und Rolle wirtschaftlich sein. **Zeitliche, personelle und ggf. finanzielle Ressourcen sind verbindlich zu planen.**

### A36 – Migration
Gemeinsam bearbeitete geeignete Vektordaten bevorzugt PostGIS, QGIS-Projekte und geeignete Fachdateien auf Fileserver, Dokumente/Austauschpakete weiterhin SharePoint. Die führende GIS-Arbeitsdatenhaltung in synchronisierten OneDrive-/SharePoint-Ordnern der Baubetreuung soll kontrolliert abgelöst werden. Vorher Inventarisierung, Konfliktklärung, Pfad-/Funktionsprüfung und fachliche Abnahme.

### A37 / A38 – Bewusst zurückgestellt
A37: Pflege, strukturelle Änderungen und Ablösung zentraler Geodatenbestände. A38: technische Integritätsregeln in PostGIS und QGIS. **Keine stillschweigende Freigabe von Option B.**

## Änderungsdisziplin

Neue Entscheidungen fortlaufend nummerieren. Änderungen bestehender Beschlüsse mit Anlass, neuem Ergebnis und betroffenen Dokumenten nachvollziehbar dokumentieren. Keine rein technische Präferenz als formalen Beschluss ausgeben.
