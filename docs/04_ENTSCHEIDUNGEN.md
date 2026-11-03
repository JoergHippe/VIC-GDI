# Architekturentscheidungen [A01](#a01)–[A38](#a38)

**Status:** Konsolidierter interner Arbeitsentwurf. Dieses Register ist die führende Stelle für Beschlussstatus und Entscheidungsbegründungen. Die knappen Zusammenfassungen ersetzen nicht die spätere Detailprüfung mit IT und Fachbereichen.

**Quellenlage:** Erstkonsolidierung aus den bisherigen Architekturgesprächen [A01](#a01)–[A38](#a38). Wo kein detailliertes Entscheidungsprotokoll vorliegt, sind die Aussagen bewusst auf die gesicherten Grundsätze begrenzt. Die Dokumente sind keine Implementierungs- oder Freigabenachweise.

**Statusschlüssel:** **B** = beschlossen; **G** = Grundsatz beschlossen, Detail offen; **Z** = zurückgestellt; **O** = offen.

| ID | Thema | Status | Festlegung / Ergebnis |
|---|---|---|---|
| <a id="a01"></a>A01 | Ausrichtung | B | Fachbereichsneutrale [GDI](ANHANG_A_GLOSSAR.md#gdi), Piloten BB und Verkehrsanlagenplanung |
| <a id="a02"></a>A02 | Datenbankorganisation | B | Gemeinsame [PostGIS](ANHANG_A_GLOSSAR.md#postgis)-Datenbank mit fachlichen Schemas |
| <a id="a03"></a>A03 | Projektbezug | B | Fachliche gemeinsame Tabellen; `project_id` selektiv, Ausnahmen zulässig |
| <a id="a04"></a>A04 | [QGIS](ANHANG_A_GLOSSAR.md#qgis)-Projekte | B | Zentrale Ressourcen, eigenständige Fach-QGIS-Projekte; getrennte Webprojekte · [überprüfungsbedürftig](#erneute-prüfung-a04-a15-und-a36) |
| <a id="a05"></a>A05 | Externe Basisdaten | B | Live bevorzugt; unveränderliche, nachvollziehbare [Snapshots](ANHANG_A_GLOSSAR.md#snapshot) bei Bedarf |
| <a id="a06"></a>A06 | Projektgeometrie | B | Optional; keine verpflichtende Projekt-[AOI](ANHANG_A_GLOSSAR.md#aoi) |
| <a id="a07"></a>A07 | Projektstammdaten | B | Schlanker gemeinsamer Kern, kein Projektmanagement |
| <a id="a08"></a>A08 | Fachbereichsübergreifende Nutzung | B | Gemeinsame Projektidentität, eindeutige Datenhoheit, keine führenden Dubletten |
| <a id="a09"></a>A09 | Datenzugriff | B | Freigegebene gemeinsame Daten lesbar, Schreiben zuständigkeitsabhängig; serverseitige Durchsetzung |
| <a id="a10"></a>A10 | [GIS](ANHANG_A_GLOSSAR.md#gis)-Server | G | [QGIS Server](ANHANG_A_GLOSSAR.md#qgis-server) bevorzugt; [PoC](ANHANG_A_GLOSSAR.md#poc) und [OGC](ANHANG_A_GLOSSAR.md#ogc)-Fähigkeiten prüfen |
| <a id="a11"></a>A11 | [Webviewer](ANHANG_A_GLOSSAR.md#webviewer) | B | Etablierte Open-Source-Lösung, gezielte Erweiterungen statt Eigenportal |
| <a id="a12"></a>A12 | [Geodatenauszug](ANHANG_A_GLOSSAR.md#extract) | G | Schlanker Extract-Service mit Rechteprüfung; Clipping/Selektion per PoC klären |
| <a id="a13"></a>A13 | Mobile Arbeit | G | [QField](ANHANG_A_GLOSSAR.md#qfield) mit [HAPPY MINI Q](ANHANG_A_GLOSSAR.md#happy-mini-q) zur Positionserfassung, etablierte Synchronisation, keine Eigenentwicklung |
| <a id="a14"></a>A14 | [ETL](ANHANG_A_GLOSSAR.md#etl) | B | Stufenweise Skript-/Importautomatisierung, keine ETL-Plattform vorab |
| <a id="a15"></a>A15 | Metadaten | B | Schlanker quellen-/datensatz-/dienstbezogener Katalog · [überprüfungsbedürftig](#erneute-prüfung-a04-a15-und-a36) |
| <a id="a16"></a>A16 | Datenqualität | B | Amtliche Daten technisch prüfen, eigene Daten pragmatisch fachlich prüfen; kein formales QA-System |
| <a id="a17"></a>A17 | QGIS-Stile | B | Zentrale [Git](ANHANG_A_GLOSSAR.md#git)-versionierte [QML](ANHANG_A_GLOSSAR.md#qml), projektspezifische Overrides |
| <a id="a18"></a>A18 | Webpublikation | B | Eigene Webkartenprojekte; primär intern, extern geschützt bei Bedarf |
| <a id="a19"></a>A19 | Web-UI | B | Eine Anwendung, einfache Grundansicht und bedarfsbezogene Erweiterungen |
| <a id="a20"></a>A20 | Suche | B | Schlanke integrierte Suche; keine separate Suchplattform |
| <a id="a21"></a>A21 | Koordinatenreferenz | B | EPSG:25832/25833 bevorzugt; Ausnahmen und Höhenbezug beachten |
| <a id="a22"></a>A22 | Raster | B | Externe Dienste bevorzugt, lokale [GeoTIFF](ANHANG_A_GLOSSAR.md#geotiff)/[COG](ANHANG_A_GLOSSAR.md#cog) nach Bedarf |
| <a id="a23"></a>A23 | Hosting | G | On-prem/[Proxmox](ANHANG_A_GLOSSAR.md#proxmox) bevorzugt; hybride Optionen möglich |
| <a id="a24"></a>A24 | Deployment | O | VM-nativ, hybrid oder containerisiert – gemeinsam mit IT entscheiden |
| <a id="a25"></a>A25 | Identitäten | G | AD/M365 und zentraler [IdP](ANHANG_A_GLOSSAR.md#idp) bevorzugt; technische Umsetzung IT-Entscheid |
| <a id="a26"></a>A26 | Berechtigungen | G | Gemeinsames Rollen-/Rechteprinzip; Durchsetzung über alle Zugriffspfade, IT-Detailklärung |
| <a id="a27"></a>A27 | Umgebungen | G | Schlanke getrennte TEST/PROD, lokale Entwicklung, Git/Migrationen; IT-Abstimmung |
| <a id="a28"></a>A28 | Backup | G | Bestehendes IT-Backup plus GDI-spezifische Sicherung/Restore; IT-Abstimmung |
| <a id="a29"></a>A29 | Monitoring | G | Bestehendes Monitoring um funktionale GIS-Prüfungen ergänzen; IT-Abstimmung |
| <a id="a30"></a>A30 | Deploymentprozess | G | Git für geeignete Ressourcen, zunächst kontrollierte Bereitstellung, später bedarfsweise automatisieren; IT-Abstimmung |
| <a id="a31"></a>A31 | Betriebsverantwortung | G | Gemeinsames GIS-/IT-Betriebsmodell, konkrete Zuständigkeiten noch abzustimmen |
| <a id="a32"></a>A32 | Support und Weiterentwicklung | B | Schlanker gemeinsamer Prozess, vorhandene Werkzeuge bevorzugen |
| <a id="a33"></a>A33 | Wissensaufbau | B | Themen-/rollenbezogen A/B/C kombinieren; Ressourcen verbindlich einplanen |
| <a id="a34"></a>A34 | Pilotstrategie | B | Gemeinsame Basis, zwei früh beteiligte und zeitlich staffelbare Piloten |
| <a id="a35"></a>A35 | [MVP](ANHANG_A_GLOSSAR.md#mvp) | B | Priorisierter anpassbarer Umfang; gemeinsame Basis und Pilot-MVPs unterscheiden |
| <a id="a36"></a>A36 | Migration | B | **B+**: verbindliche Zielarchitektur, selektive Migration, problematische [SharePoint](ANHANG_A_GLOSSAR.md#sharepoint)-/[OneDrive](ANHANG_A_GLOSSAR.md#onedrive)-GIS-Arbeitsbestände ablösen · [überprüfungsbedürftig](#erneute-prüfung-a04-a15-und-a36) |
| <a id="a37"></a>A37 | Datenlebenszyklus | Z | Option B plausibel, aber nicht beschlossen; später klären |
| <a id="a38"></a>A38 | Datenbankregeln | Z | Option B plausibel, aber nicht beschlossen; später klären |

## Erneute Prüfung [A04](#a04), [A15](#a15) und [A36](#a36)

Die Kennzeichnung ergänzt den bisherigen Status. Bis zu einer dokumentierten Folgeentscheidung gelten die bisherigen Festlegungen.

| Bezug | Neue Präferenz zur Prüfung | Vor einer Änderung klären |
|---|---|---|
| [A04](#a04) | QGIS-Projekte zentral in [PostgreSQL](ANHANG_A_GLOSSAR.md#postgresql) ablegen. Fachprojekte und getrennte Webprojekte bleiben der Ausgangspunkt. | Umfang, Projekt- und Publikationsrechte, parallele Bearbeitung, Versionierung, externe Ressourcen und Wiederherstellung. QGIS unterstützt Projektablage in PostgreSQL. [QGIS-Dokumentation](https://docs.qgis.org/testing/en/docs/user_manual/introduction/project_files.html#managing-qgis-project-files-from-postgresql-databases) |
| [A15](#a15) | Internen Katalog über den bisherigen schlanken Umfang hinaus erweitern und Metadaten hybrid pflegen. | Welche Suche und Felder bringen Nutzen? Technisch ableitbare Angaben wie Schema oder Importzeit automatisiert übernehmen. Fachliche Angaben wie Zweck, Zuständigkeit und Nutzungsauflagen redaktionell pflegen und freigeben. Führende Quelle je Feld und Aktualisierung bei Konflikten klären. |
| [A36](#a36) | Zentrale PostgreSQL-Projektablage als Ziel für geeignete Projekte prüfen. | Projektinventar, Pfade und externe Dateien, Rechte, Übernahme, Rückfallweg und fachliche Abnahme. Selektive Migration und kontrollierte Ablösung problematischer Synchronisationsordner bleiben der Ausgangspunkt. |

### Prüfrahmen für die Projektablage ([A04](#a04)/[A36](#a36))

Für eine spätere, gesondert freigegebene Erprobung genügt ein repräsentatives Projekt mit PostGIS-Vektordaten und einer referenzierten Rasterdatei, zwei QGIS-Arbeitsplätzen und getrennten Rollen.

- **Grundfunktion:** Projekt speichern und mit dem zweiten Konto öffnen. Leserecht, verweigertes Überschreiben und erreichbare Rasterreferenzen prüfen.
- **Zusammenarbeit:** Gleichzeitige Änderungen an Vektordaten und konkurrierende Änderungen an der Projektdefinition getrennt betrachten. Das Konfliktverhalten muss nachvollziehbar sein. Für Datenänderungen ist ein Umgang ohne unkontrollierten Verlust erforderlich.
- **Wiederherstellung:** Einen praktikablen Weg zu einem früheren Projektstand samt benötigten Ressourcen prüfen.
- **Webpublikation:** Bei vorgesehener Webnutzung zusätzlich Kartenbereitstellung über QGIS Server mit den vorgesehenen Rechten prüfen. Die Desktop-Eignung separat bewerten.

### Katalogumfang und Standards ([A15](#a15))

Priorisierte Suchfälle und vorhandene Quellen bestimmen den Katalogumfang. [OGC API – Records](https://docs.ogc.org/is/20-004r1/20-004r1.html) kann als Referenz für die Auffindbarkeit dienen. Eine Katalogsoftware oder Schnittstelle wird erst bei konkretem Bedarf ausgewählt.

## Erläuterungen zu entscheidenden Festlegungen

### [A09](#a09) / [A26](#a26) – Datenhoheit und Rechte
Eine fachlich führende Stelle je gemeinsamem Datenbestand. Lesende fachbereichsübergreifende Nutzung nach Freigabe, Schreibrechte nach Rolle und Zuständigkeit. Die Durchsetzung muss in DB, Diensten, Extract und mobilen Pfaden wirksam sein; das konkrete Berechtigungsdesign ist offen.

### [A12](#a12) – Extract
Geplante Formate [GPKG](ANHANG_A_GLOSSAR.md#geopackage), [Shapefile](ANHANG_A_GLOSSAR.md#shapefile), [GeoJSON](ANHANG_A_GLOSSAR.md#geojson) und CSV; Flächenauswahl aus Karte, GeoJSON/Shapefile oder [BBox](ANHANG_A_GLOSSAR.md#bbox) und optional Ziel-[CRS](ANHANG_A_GLOSSAR.md#crs). **Selektion ganzer Objekte ist nicht gleich geometrischem Zuschnitt.** Diese Unterscheidung ist vor Implementierung zu erproben.

### [A24](#a24) – Deployment
Die Varianten **A native VMs**, **B Datenbank nativ plus containerisierte GIS-Dienste**, **C umfassende Containerisierung** bleiben gleichberechtigte Untersuchungsoptionen. Vergleich nach Betrieb, IT-Know-how, Sicherheit, Wartbarkeit, Backup, Kosten und Zukunftsfähigkeit; kein voreiliger Technologieentscheid.

### [A33](#a33) – Wissensaufbau
Eigenständige Einarbeitung, gezielte Schulungen und umfangreiche Schulung/Zertifizierung können je Thema und Rolle wirtschaftlich sein. **Zeitliche, personelle und ggf. finanzielle Ressourcen sind verbindlich zu planen.**

### [A36](#a36) – Migration
Gemeinsam bearbeitete geeignete Vektordaten bevorzugt PostGIS, QGIS-Projekte und geeignete Fachdateien auf Fileserver, Dokumente/Austauschpakete weiterhin SharePoint. Die führende GIS-Arbeitsdatenhaltung in synchronisierten OneDrive-/SharePoint-Ordnern der Baubetreuung soll kontrolliert abgelöst werden. Vorher Inventarisierung, Konfliktklärung, Pfad-/Funktionsprüfung und fachliche Abnahme.

### [A37](#a37) / [A38](#a38) – Bewusst zurückgestellt
[A37](#a37): Pflege, strukturelle Änderungen und Ablösung zentraler Geodatenbestände. [A38](#a38): technische Integritätsregeln in PostGIS und QGIS. **Keine stillschweigende Freigabe von Option B.**

## Änderungsdisziplin

Neue Entscheidungen fortlaufend nummerieren. Änderungen bestehender Beschlüsse mit Anlass, neuem Ergebnis und betroffenen Dokumenten nachvollziehbar dokumentieren. Keine rein technische Präferenz als formalen Beschluss ausgeben.
