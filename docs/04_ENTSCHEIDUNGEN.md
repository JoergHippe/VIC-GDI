# Festlegungs- und Entscheidungsregister A01–A39

**Status:** Konsolidierter interner Arbeitsentwurf. Dieses Register ist die **führende Stelle für den aktuellen fachlichen Festlegungs- und Entscheidungsstand**, nicht der Nachweis einer Projekt-, Budget- oder Betriebsfreigabe durch Geschäftsführung oder IT. Fachliche Ausgangslage und übergeordnete Prinzipien: [Projektkonzept](01_PROJEKTKONZEPT.md#projektgrundsätze).

**Einordnung:** Die früher pauschal als „Architekturentscheidungen“ bezeichneten A01–A39 enthalten unterschiedliche Arten von Festlegungen. Die Kennungen sind **dauerhaft stabil**; Kategorie, Status und Priorität sind davon unabhängig. Eine Festlegung kann Grundsatz **und** konkrete Ausprägung enthalten; die Tabelle benennt ihre primäre Kategorie.

- **Kategorie:** Grundsatz = verbindliche Projektleitplanke bzw. Ausgangsvorgabe; Architektur/Daten = technische oder Datenmodellgestaltung; Fachfunktion = konkreter fachlicher Funktionsumfang; Betrieb/Organisation = sichere Bereitstellung und dauerhafte Verantwortung.
- **Status:** **B** = fachlich beschlossen; **G** = Grundsatz beschlossen, Details offen; **Z** = bewusst zurückgestellt; **O** = offen. **B/G bedeuten keine formale GF-/IT-Umsetzungsfreigabe.**
- **Prioritäten:** Bearbeitungszeitpunkt P0–P3 ausschließlich bei [offenen Punkten](08_OFFENE_PUNKTE.md#arbeitspriorität-nach-entscheidungshorizont), nicht in der ID. Eine offene Detailklärung hebt einen weiterhin geltenden Grundsatz nicht auf.

## Register

| ID | Kategorie | Thema | Status | Kernaussage |
|---|---|---|---|---|
| <a id="a01"></a>A01 | Grundsatz | Ausrichtung | B | Fachbereichsneutrale GDI; zwei Pilotbereiche im Einführungskonzept. |
| <a id="a02"></a>A02 | Grundsatz | Datenbankorganisation | B | PostgreSQL/PostGIS ist die gesetzte zentrale Geodatenbasis; gemeinsame Datenbank mit fachlichen Schemas. |
| <a id="a03"></a>A03 | Architektur/Daten | Projektbezug | B | Projektzuordnung für gemeinsame Fachtabellen selektiv über `project_id`; fachlich begründete Ausnahmen. |
| <a id="a04"></a>A04 | Architektur/Daten | [QGIS](ANHANG_A_GLOSSAR.md#qgis)-Projekte | B | Zentrale Ressourcen, eigenständige Fach-QGIS-Projekte und getrennte Webprojekte; Projektablage erneut prüfen. |
| <a id="a05"></a>A05 | Architektur/Daten | Externe Basisdaten | B | Live bevorzugt; unveränderliche, nachvollziehbare [Snapshots](ANHANG_A_GLOSSAR.md#snapshot) bei Bedarf |
| <a id="a06"></a>A06 | Architektur/Daten | Projektgeometrie | B | Optional; keine verpflichtende Projekt-[AOI](ANHANG_A_GLOSSAR.md#aoi) |
| <a id="a07"></a>A07 | Grundsatz | Projektstammdaten | B | Schlanke gemeinsame Projektstammdaten; kein Projektmanagementsystem. |
| <a id="a08"></a>A08 | Grundsatz | Fachbereichsübergreifende Nutzung | B | Gemeinsame Projektidentität, klare fachliche Datenhoheit, keine redundanten führenden Bestände. |
| <a id="a09"></a>A09 | Grundsatz | Datenzugriff | B | Freigegebene gemeinsame Daten lesbar, Schreiben zuständigkeitsabhängig; serverseitige Durchsetzung |
| <a id="a10"></a>A10 | Architektur/Daten | [GIS](ANHANG_A_GLOSSAR.md#gis)-Server | G | [QGIS Server](ANHANG_A_GLOSSAR.md#qgis-server) bevorzugt; [PoC](ANHANG_A_GLOSSAR.md#poc) und [OGC](ANHANG_A_GLOSSAR.md#ogc)-Fähigkeiten prüfen |
| <a id="a11"></a>A11 | Grundsatz | [Webviewer](ANHANG_A_GLOSSAR.md#webviewer) | B | Etablierte freie Webviewer-Software vor Eigenentwicklung; Erweiterungen nur gezielt. |
| <a id="a12"></a>A12 | Fachfunktion | [Geodatenauszug](ANHANG_A_GLOSSAR.md#extract) | G | Berechtigter Export als Funktion statt Pflicht zu eigenem Dienst; vollständige Objektselektion, optional Clipping; GPKG/GeoJSON/DXF/CSV, Shapefile optional; CRS-Auswahl; Rechteausgestaltung offen. |
| <a id="a13"></a>A13 | Fachfunktion | Mobile Arbeit | G | Bestehende BB-Praxis: QField und HAPPY MINI Q; Übertragungsweg offen, keine eigene Synchronisationsplattform. |
| <a id="a14"></a>A14 | Grundsatz | [ETL](ANHANG_A_GLOSSAR.md#etl) | B | Stufenweise Skript-/Importautomatisierung, keine ETL-Plattform vorab |
| <a id="a15"></a>A15 | Architektur/Daten | Metadaten | B | Interner Metadatenkatalog als Basis; Umfang und hybride Datenpflege erneut prüfen. |
| <a id="a16"></a>A16 | Fachfunktion | Datenqualität | B | Technische Eingangsprüfung amtlicher Daten, angemessene Fachprüfung eigener Daten; kein umfassendes formales QA-System. |
| <a id="a17"></a>A17 | Architektur/Daten | QGIS-Stile | B | Zentrale [Git](ANHANG_A_GLOSSAR.md#git)-versionierte [QML](ANHANG_A_GLOSSAR.md#qml), projektspezifische Overrides |
| <a id="a18"></a>A18 | Architektur/Daten | Webpublikation | B | Eigene Webkartenprojekte; primär intern, extern geschützt bei Bedarf |
| <a id="a19"></a>A19 | Fachfunktion | Web-UI | B | Eine Anwendung, einfache Grundansicht und bedarfsbezogene Erweiterungen |
| <a id="a20"></a>A20 | Fachfunktion | Suche | B | Schlanke integrierte Suche; keine separate Suchplattform |
| <a id="a21"></a>A21 | Fachfunktion | Koordinatenreferenz | B | ETRS89/UTM EPSG:25832/25833 bevorzugt; EPSG:3068 unterstützen, weitere Lage-/Höhenbezüge bedarfsabhängig. |
| <a id="a22"></a>A22 | Architektur/Daten | Raster | B | Externe Dienste bevorzugt, lokale [GeoTIFF](ANHANG_A_GLOSSAR.md#geotiff)/[COG](ANHANG_A_GLOSSAR.md#cog) nach Bedarf |
| <a id="a23"></a>A23 | Betrieb/Organisation | Hosting | G | On-prem/Proxmox als Ausgangspräferenz, hybride Lösungen möglich; Hosting-/Bezugsmodell H1–H4 offen. |
| <a id="a24"></a>A24 | Betrieb/Organisation | Deployment | O | [VM](ANHANG_A_GLOSSAR.md#vm)-nativ, hybrid oder containerisiert – gemeinsam mit IT entscheiden |
| <a id="a25"></a>A25 | Betrieb/Organisation | Identitäten | G | AD/M365 und zentraler [IdP](ANHANG_A_GLOSSAR.md#idp) bevorzugt; technische Umsetzung IT-Entscheid |
| <a id="a26"></a>A26 | Betrieb/Organisation | Berechtigungen | G | Gemeinsames Rollen-/Rechteprinzip über alle tatsächlichen Zugriffspfade durchsetzen; Rollen und Granularität offen. |
| <a id="a27"></a>A27 | Betrieb/Organisation | Umgebungen | G | Schlanke getrennte TEST/PROD, lokale Entwicklung, Git/Migrationen; IT-Abstimmung |
| <a id="a28"></a>A28 | Betrieb/Organisation | Backup | G | Bestehendes IT-Backup plus GDI-spezifische Sicherung/Restore; IT-Abstimmung |
| <a id="a29"></a>A29 | Betrieb/Organisation | Monitoring | G | Bestehendes Monitoring um funktionale GIS-Prüfungen ergänzen; IT-Abstimmung |
| <a id="a30"></a>A30 | Betrieb/Organisation | Deploymentprozess | G | Git für geeignete Ressourcen, zunächst kontrollierte Bereitstellung, später bedarfsweise automatisieren; IT-Abstimmung |
| <a id="a31"></a>A31 | Betrieb/Organisation | Betriebsverantwortung | G | Gemeinsames GIS-/IT-Betriebsmodell, konkrete Zuständigkeiten noch abzustimmen |
| <a id="a32"></a>A32 | Betrieb/Organisation | Support und Weiterentwicklung | B | Schlanker gemeinsamer Prozess, vorhandene Werkzeuge bevorzugen |
| <a id="a33"></a>A33 | Grundsatz | Wissensaufbau | B | Themen-/rollenbezogen A/B/C kombinieren; Ressourcen verbindlich einplanen |
| <a id="a34"></a>A34 | Grundsatz | Pilotstrategie | B | Gemeinsame GDI-Basis; zwei früh beteiligte, zeitlich staffelbare Pilotbereiche. |
| <a id="a35"></a>A35 | Grundsatz | [MVP](ANHANG_A_GLOSSAR.md#mvp) | B | Schlanker priorisierter MVP; GDI-Basis und fachliche Pilotumfänge unterscheiden. |
| <a id="a36"></a>A36 | Grundsatz | Migration | B | Migrationslinie B+: verbindliche Zielarchitektur, selektive Ablösung problematischer synchronisierter GIS-Arbeitsbestände; Projektablage erneut prüfen. |
| <a id="a37"></a>A37 | Architektur/Daten | Datenlebenszyklus | Z | Option B plausibel, aber nicht beschlossen; später klären |
| <a id="a38"></a>A38 | Architektur/Daten | Datenbankregeln | Z | Konkrete DB-/QGIS-Fachvalidierungen zurückgestellt; grundlegende Datenintegrität bleibt verpflichtend. |
| <a id="a39"></a>A39 | Betrieb/Organisation | Umsetzungs-, Qualifizierungs-, Betriebs- und Hostingmodell | O | Vier offene Dimensionen: Umsetzung, Wissensaufbau, Betriebsverantwortung und Hosting/Bezug (H1–H4); Entscheidung durch GF und IT. |

## Erneute Prüfung A04, A15 und A36

**Prüfvorbehalt, kein Widerruf:** Die Grundfestlegungen gelten weiter, bis eine ausdrücklich dokumentierte Folgeentscheidung sie verändert. Prüfbedarf und Realisierung sind keine zusätzlichen Beschlüsse.

| Bezug | Bestehender Rahmen | Offener Prüfpunkt |
|---|---|---|
| [A04](#a04) | Eigenständige Fach-QGIS-Projekte, getrennte Webprojekte, gemeinsame Ressourcen | Zentrale QGIS-Projektablage in PostgreSQL: Rechte, Parallelität, Versionierung, externe Ressourcen, Wiederherstellung und QGIS-Server-Eignung |
| [A15](#a15) | Internes Metadatenverzeichnis für Quellen, Daten und Dienste | Tatsächliche Such-/Pflegefelder, hybride automatische/manuelle Metadatenpflege, Feldhoheit und ggf. Katalogschnittstellen |
| [A36](#a36) | Selektive Migration, problematische synchronisierte GIS-Arbeitsbestände kontrolliert ablösen | Geeignete QGIS-Projekte für zentrale Ablage, Inventar, Konflikte, Pfade, Rückfallweg und fachliche Abnahme |

Konkrete Prüfaufträge und Zeitpunkt: [offene Punkte](08_OFFENE_PUNKTE.md). QGIS-Projektablage wird unterstützt, aber die betriebliche Eignung muss im Pilot geprüft werden: [QGIS-Dokumentation](https://docs.qgis.org/testing/en/docs/user_manual/introduction/project_files.html#managing-qgis-project-files-from-postgresql-databases).

### Prüfrahmen für die Projektablage (A04/A36)

Für einen später freigegebenen Test reichen ein repräsentatives Projekt mit PostGIS-Vektordaten und Rasterreferenz, zwei Arbeitsplätze und getrennte Rollen. Zu prüfen sind **Lesen/Schreiben, konkurrierende Projektänderungen gegenüber Datenänderungen, externe Ressourcen, Wiederherstellung** sowie bei Webbedarf die eigenständige QGIS-Server-Tauglichkeit. Die konkrete Durchführung gehört in [offene Punkte](08_OFFENE_PUNKTE.md) bzw. den Pilotplan; dies ist noch kein freigegebener PoC.

### Katalogumfang und Standards (A15)

Automatisierbare technische Angaben (z. B. Schema, Importzeit) und redaktionelle Fachangaben (Zweck, Verantwortung, Nutzungsauflagen) unterscheiden. Feldführerschaft, Aktualisierung und tatsächlichen Suchbedarf noch festlegen. [OGC API – Records](https://docs.ogc.org/is/20-004r1/20-004r1.html) ist eine mögliche Schnittstellenreferenz, **keine beschlossene Katalogsoftware**. Bewertung: [SW-04](software/04_METADATENKATALOG.md).

## Wesentliche Abgrenzungen und Begründungen

### A02/A03 – Geodatenbasis und Projektbezug

PostGIS ist als zentrale Basis gesetzt; **eine gemeinsame Datenbank mit Fachschemas** konkretisiert dies architektonisch. Nicht alle Geodaten oder Fachdateien müssen in PostGIS liegen. `project_id` ist nur dort zweckmäßig, wo ein realer Projektbezug besteht; keine pauschale Pflicht für jede Tabelle. [Architektur](03_ARCHITEKTUR.md#datenorganisation).

### A08/A09/A26 – Datenhoheit und Rechte

Eine fachlich führende Stelle je Datenbestand; berechtigter fachbereichsübergreifender Lesezugriff, Schreiben nach Verantwortung und Rolle. **Direkter Datenbankzugriff, Dienste, Export und mobile Nutzung** müssen wirksam abgesichert sein. Das konkrete Rollen-/Rechtemodell bleibt mit der IT zu klären.

### A12/A21 – Berechtigter Geodatenauszug

**Beschlossen:** Export als Funktion ohne Pflicht zu eigenem Dienst (Option A); vollständige Objektselektion für vom Auswahlgebiet betroffene Objekte als Standard, Clipping als bewusst wählbare Zusatzoption (Punkt 1/C); GPKG, klassisches GeoJSON (GeoJSON 2008), DXF und CSV; Shapefile optional. Quell-/wählbares Ziel-CRS einschließlich EPSG:25832/25833/3068. RFC 7946 mit WGS84/CRS84 nur als optionaler GeoJSON-Sondermodus.

**Offen:** konkrete Rollen-/Rechtegranularität (Punkt 3/D) und technische Validierung. Vollständige Objekte dürfen **keine räumlichen Rechtebeschränkungen umgehen**; ungeschützte Exportwege nicht produktiv freischalten. Vorgaben zu GeoJSON-CRS, DXF-Einheiten, Transformationen, Herkunft und Geometrie-/Attributkorrektheit sowie Testfälle stehen führend im [SW-06-Prüfkatalog](software/06_GEODATENAUSZUG.md); [A26](#a26) gilt unabhängig davon.

### A23/A24/A39 – Hosting, technische Bereitstellung und Zuständigkeit

**A23:** On-prem/Proxmox ist die Ausgangspräferenz, keine ausschließliche Festlegung. **A24:** Natives VM-Deployment, Mischbetrieb oder umfassende Containerisierung bleiben bis zur IT-Entscheidung offen. **A39:** Umsetzung, Qualifizierung, Betrieb (D1–D3) und Hosting/Bezug (H1–H4) sind getrennte offene Entscheidungsdimensionen. H2 ist **eigene GDI auf gemieteter Infrastruktur**, H3 **betreute Mietinfrastruktur**, H4 **GDIaaS** (zuvor C3). Keine dieser Varianten gilt als ausgewählt. Vergleich und Zuständigkeiten: [Umsetzungs- und Betriebsmodelle](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md).

### A33/A34/A35 – Wissen und stufenweise Einführung

Rollenbezogenen Wissensaufbau **mit Zeit, Personen und gegebenenfalls Budget** einplanen. Gemeinsame technische Basis und zwei gestaffelte Piloten; konkrete erste Anwendungsfälle und MVP-Umfang noch priorisieren. [Roadmap](07_ROADMAP.md), [Pilotkonkretisierung](05_PILOTKONKRETISIERUNG.md).

### A36 – Selektive Migration

Geeignete gemeinsam bearbeitete Vektordaten bevorzugt nach PostGIS; Fachdateien bei Bedarf auf Fileservern, Dokumente/Austauschpakete weiterhin in SharePoint. Problematische synchronisierte SharePoint-/OneDrive-GIS-Arbeitsbestände der Baubetreuung kontrolliert ablösen. Inventar, Konflikte, Pfade und fachliche Abnahme sind erforderlich; zentraler PostgreSQL-Projektspeicher bleibt gesondert zu prüfen.

### A37/A38 – Zurückgestellt, aber keine Sicherheitsausnahme

Lebenszyklusdetails und spezifische DB-/QGIS-Validierungsregeln (jeweils bisher Option B) sind **nicht beschlossen**. Das hebt weder grundlegende Datenintegrität noch Rechte, Nachvollziehbarkeit und Wiederherstellbarkeit auf. Ausgestaltung erst bei tatsächlichem Pilot-/Umsetzungsbedarf.

## Änderungsdisziplin

Neue Kennungen fortlaufend vergeben; **nicht nach Priorität umnummerieren**. Änderung eines bestehenden Beschlusses mit Anlass, Ergebnis und Auswirkungen dokumentieren. Die fachlich führende Stelle für Umsetzungstests, Kandidatenvergleiche und Prüfschritte bleibt jeweils das zuständige Dokument; dieses Register ist **kein zweites technisches Lastenheft**. Keine Empfehlung als Beschluss ausgeben.
