# SW-06 – Geodatenauszug / Export

**Status:** Erstes Bewertungsgerüst · **Entscheidung:** offen · **Stand:** 04.11.2026  
**Entscheidungsbezug:** [A12](../04_ENTSCHEIDUNGEN.md#a12) · [Methodik](BEWERTUNGSMETHODIK.md)

## 1. Zweck und Abgrenzung

Berechtigte Nutzer sollen ausgewählte Geodaten in passenden Formaten und ggf. räumlich begrenzten Ausschnitten exportieren können. Das kann ein einfacher QGIS-Arbeitsablauf, eine vorhandene Viewer-/Serverfunktion oder erst bei nachgewiesenem Bedarf ein schlanker gesicherter Auszugsdienst sein.

**Abgrenzung:** [A12 – Option A](../04_ENTSCHEIDUNGEN.md#a12) legt die **Funktion des berechtigten Geodatenauszugs** fest, nicht einen eigenständigen Extract-Service. Zuerst sind vorhandene Funktionen zu prüfen; eine zusätzliche Plattform kommt nur bei nachgewiesenem Bedarf infrage. Die technische Differenz zwischen **Objektselektion** und **tatsächlichem geometrischem Clipping** ist fachlich entscheidend. Rechte müssen auch bei direkten API-/Dienstaufrufen gelten.

## 2. Besondere Anforderungen

- **Muss:** Auszug nur aus explizit autorisierten Layern und Datenbeständen; keine Rechteumgehung durch Exportpfade.
- **Muss:** Benötigte Formate und **formatverträgliche CRS** mit nachvollziehbarer Auswahl, korrekter Transformation und Geometrie-/Attributbehandlung. **GeoJSON nach [RFC 7946](https://www.rfc-editor.org/rfc/rfc7946#section-4)** ist auf WGS 84/CRS84 (Länge/Breite) festgelegt; für EPSG:25832/25833 z. B. GeoPackage wählen.
- **Soll:** Nutzerfreundlicher Ablauf auch ohne umfangreiche GIS-Kenntnisse, soweit Pilotbedarf.
- **Offen:** Formate (GPKG, GeoJSON, Shapefile, CSV), Größe, Auszugsfläche, Objektselektion versus Clipping, automatisierter Abruf.

| Frage | QGIS-Desktop-Bordmittel | Vorhandene Viewer-/Dienstfunktionen | Schlanker GDAL-/OGR-Auszug |
|---|---|---|---|
| Rechteprüfung für alle tatsächlich genutzten Exportwege | ? | ? | ? |
| Korrekte Geometrien, Attribute und Raumbezüge im Pilotfall | ? | ? | ? |

**Hinweis:** `?` bedeutet **noch nicht nachgewiesen**, nicht `nicht erfüllt`.

## 3. Kandidaten (noch keine Auswahl)

| Kandidat | Charakter / Prüfansatz | Ausgangsquelle |
|---|---|---|
| **QGIS-Desktop-Bordmittel** | Vorhandene Export-/Selektionsfunktionen bei Fachanwendern nutzen. | [Projekt-/Herstellerdokumentation](https://docs.qgis.org/3.44/en/docs/user_manual/) |
| **Vorhandene Viewer-/Dienstfunktionen** | Exportmöglichkeiten der späteren Webkomponenten gezielt verwenden. | [Projekt-/Herstellerdokumentation](https://docs.qwc.app/) |
| **Schlanker GDAL-/OGR-Auszug** | Nur bei Bedarf eigener abgesicherter Ablauf mit etabliertem GDAL/OGR-Backend. | [Projekt-/Herstellerdokumentation](https://gdal.org/en/stable/programs/ogr2ogr.html) |

## 4. Vergleichsmatrix

Standardisierte Dimensionen und Gewichte nach [Methodik](BEWERTUNGSMETHODIK.md); `0–3` nur nach Quellenprüfung bzw. Test, sonst `?`.

**Produkt-/Release-Recherche noch ausstehend:** `?` = noch nicht geprüft, `n. a.` = kein eigenständig versioniertes Produkt bzw. gegenwärtig keine konkrete Software ausgewählt. Beim tatsächlichen Vergleich Erstveröffentlichung, Version samt Releasedatum und Aktivität der letzten 12 Monate mit offiziellem Release-/Changelog-Beleg und Bewertungsstichtag ergänzen. Diese drei Angaben werden nicht zusätzlich bepunktet.

| Dimension (Gewicht) | QGIS-Desktop-Bordmittel | Vorhandene Viewer-/Dienstfunktionen | Schlanker GDAL-/OGR-Auszug |
|---|---:|---:|---:|
| **Erstveröffentlichung / seit (Jahr)** | ? | n. a. (abhängig vom Viewer) | n. a. (noch keine Eigenlösung) |
| **Aktuelle stabile Version (Releasedatum)** | ? | n. a. (abhängig vom Viewer) | n. a. (noch keine Eigenlösung) |
| **Entwicklungsaktivität (12 Monate)** | ? | n. a. (abhängig vom Viewer) | n. a. (noch keine Eigenlösung) |
| Fachliche/funktionale Eignung (30 %) | ? | ? | ? |
| Integration/Interoperabilität (20 %) | ? | ? | ? |
| Sicherheit/Berechtigungen (15 %) | ? | ? | ? |
| Betrieb/Wartbarkeit (15 %) | ? | ? | ? |
| Reife/Zukunftsfähigkeit (10 %) | ? | ? | ? |
| Kosten/Lizenzen (10 %) | ? | ? | ? |
| **Gesamt (noch nicht berechenbar)** | — | — | — |
| **Evidenzstand** | E0 | E0 | E0 |

## 5. Vor- und Nachteile – vorläufige Prüfhypothesen

**QGIS-Desktop-Bordmittel:** Keine zusätzliche Plattform nötig; für Gelegenheitsnutzer außerhalb QGIS kann der Ablauf zu technisch sein. **Noch zu verifizieren:** Bedienbarkeit, räumlicher Zuschnitt, Berechtigungen und reproduzierbarer Ablauf.

**Vorhandene Viewer-/Dienstfunktionen:** Direkter Export aus dem Browser kann bequem sein; Funktionsumfang und vor allem serverseitige Rechte müssen konkret geprüft werden. **Noch zu verifizieren:** Wird echter Zuschnitt angeboten? Wie werden Datei- und Direktaufrufe abgesichert?

**Schlanker GDAL-/OGR-Auszug:** Standardwerkzeuge ermöglichen wiederholbare Konvertierungen und Clipping; die sichere Web-/Job-Einbindung erzeugt zusätzlichen Entwicklungs- und Betriebsaufwand. **Noch zu verifizieren:** Auftragssteuerung, Rechtegrenzen, große Datensätze, Dateihandling und Testabdeckung.

## 6. Bewertung und Empfehlung

**Beschlossene Leitplanke:** A12 verlangt den berechtigten Auszug als Funktion, **keinen eigenen Serverdienst**. **Softwareauswahl weiterhin offen:** QGIS- und Viewer-/Dienst-Bordmittel haben Vorrang; falls sie die bestätigten Anforderungen nicht erfüllen, ist ein zusätzlicher Dienst begründet zu prüfen. Eine belastbare Produktempfehlung steht noch aus.

**Nächster Schritt:** Anhand eines Pilotlayers zwei Fälle testen: vollständige Objektselektion und echtes Clipping einer definierten Fläche; dazu Benutzerrechte, Zielformat, CRS, Maße/Geometrien und Bedienaufwand vergleichen.

## 7. Quellen und Stand

- [QGIS Benutzerhandbuch](https://docs.qgis.org/3.44/en/docs/user_manual/) – offizielle Dokumentation; vorhandene Auswahl-/Export-Funktionen
- [GDAL/OGR – ogr2ogr](https://gdal.org/en/stable/programs/ogr2ogr.html) – offizielle Dokumentation; Filter, räumlicher Zuschnitt, Konvertierung und CRS
- [RFC 7946 § 4 – Coordinate Reference System](https://www.rfc-editor.org/rfc/rfc7946#section-4) – verbindlicher CRS-Rahmen bei standardkonformem GeoJSON
- [GDAL RFC 65 – GeoJSON RFC 7946](https://gdal.org/en/stable/development/rfc/rfc65_rfc7946_geojson.html) – konkrete Implementierung/Transformation bei GDAL-Ausgabe
- [QWC-Dokumentation](https://docs.qwc.app/) – offizielle Projektdoku; mögliche Webviewer-/Dienstintegrationen; Auswahl noch offen
- [VIC-GDI Entscheidung A12](../04_ENTSCHEIDUNGEN.md#a12) – intern; Fachgrenzen des Auszugs

**Quellenstand:** Ausgangslinks am 04.11.2026 zusammengestellt; **keine vollständige Release-, Lizenz-, Sicherheits- oder Praxistestprüfung**. Unabhängige Bewertungen und Erfahrungsberichte sowie ggf. PoC-Ergebnisse werden beim echten Vergleich mit Version und Datum ergänzt.
