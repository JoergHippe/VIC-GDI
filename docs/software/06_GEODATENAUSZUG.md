# SW-06 – Geodatenauszug / Export

**Status:** Erstes Bewertungsgerüst · **Funktionsentscheidungen A12:** Punkte 1 und 2 beschlossen, Berechtigungsmodell Punkt 3 offen · **Softwareauswahl:** offen · **Stand:** 04.11.2026  
**Entscheidungsbezug:** [A12](../04_ENTSCHEIDUNGEN.md#a12) · [Methodik](BEWERTUNGSMETHODIK.md)

## 1. Zweck und Abgrenzung

Berechtigte Nutzer sollen ausgewählte Geodaten in passenden Formaten und ggf. räumlich begrenzten Ausschnitten exportieren können. Das kann ein einfacher QGIS-Arbeitsablauf, eine vorhandene Viewer-/Serverfunktion oder erst bei nachgewiesenem Bedarf ein schlanker gesicherter Auszugsdienst sein.

**Abgrenzung:** [A12](../04_ENTSCHEIDUNGEN.md#a12) verlangt die **Exportfunktion**, keinen eigenen Dienst; vorhandene Bordmittel zuerst. **Beschlossen:** (1) **vollständige Objektselektion als Standard**, **geometrisches Clipping optional**; (2) **GPKG, GeoJSON, DXF und CSV**, **Shapefile optional**, Quell-/wählbares Ziel-CRS inkl. EPSG:25832, 25833 und 3068. **Nicht beschlossen:** (3) konkrete Rollen-/Rechteausgestaltung – siehe [A26](../04_ENTSCHEIDUNGEN.md#a26). Zugriffsschutz muss auf allen tatsächlich genutzten Exportwegen wirksam sein.

## 2. Besondere Anforderungen

- **Muss:** Nur nach wirksamem Datenzugriffsrecht exportieren; ein noch offenes Rollenmodell bedeutet **keine** Freigabe aller Daten. Direkter DB-Zugriff, Dienst/API, Exportauftrag und Download separat betrachten.
- **Muss:** **Vollständige Objektselektion** (Objekte, die das Auswahlgebiet schneiden) als Standard, **zusätzlich optional echtes Clipping**; gekappte Geometrien, ursprüngliche Objekt-ID, Herkunft und ggf. neu berechnete Kennwerte fachlich korrekt behandeln. Bei räumlichen Rechtegrenzen vollständige Objekte **nicht** unberechtigt ausgeben.
- **Muss:** GPKG, GeoJSON, DXF und CSV als **vorgesehene Exportformate** berücksichtigen; Shapefile als **optionales** Kompatibilitätsformat. Tatsächliche Abdeckung und Qualität mit dem gewählten Werkzeug nachweisen; weitere Formate nur nach Bedarf.
- **Muss:** Quell-CRS unverändert ausgeben können oder fachlich gewünschte Ziel-CRS transformieren, soweit das Zielformat dies unterstützt; **EPSG:25832, 25833 und 3068 (Soldner Berlin)** explizit prüfen. Transformationsgenauigkeit, ggf. erforderliche Gitter und Höhenbezüge gesondert bewerten.
- **Muss:** **Klassisches GeoJSON (GeoJSON 2008)** mit nicht-WGS84-CRS **explizit kennzeichnen**, empfangendes System auf CRS-Interpretation testen; **RFC 7946** (WGS 84/CRS84, Länge/Breite) ist **nur ein wählbarer Sondermodus**, nicht die Vorgabe für VIC-GDI.
- **Muss:** DXF-GIS/CAD-Export mit dokumentiertem CRS und Zeichnungseinheiten (Datei allein nicht verlässlich georeferenziert); Geometrie-/Layer-/Attributabbildung auf tatsächlichen CAD-Clients prüfen. CSV für Attribute bzw. vereinbarte Punktkoordinaten inkl. CRS-Bezeichnung.
- **Soll:** Nutzerfreundlicher Ablauf auch für Gelegenheitsanwender, sofern ein Pilot es erfordert.
- **Offen:** Exakte Rollen-/Rechtegranularität nach [A26](../04_ENTSCHEIDUNGEN.md#a26), konkrete Pilotfälle und Exportbedienung, Größe/Performance, notwendige Automatisierung und zusätzliche Backenddienste.

| Frage | QGIS-Desktop-Bordmittel | Vorhandene Viewer-/Dienstfunktionen | Schlanker GDAL-/OGR-Auszug |
|---|---|---|---|
| Rechteprüfung für alle tatsächlich genutzten Exportwege | ? | ? | ? |
| Korrekte Geometrien, Attribute und Raumbezüge im Pilotfall | ? | ? | ? |
| Objektselektion und Clipping; Herkunft und Attributwerte | ? | ? | ? |
| DXF mit CRS-/Einheiteninformation; EPSG:3068-Transformation | ? | ? | ? |
| GeoJSON 2008 mit explizitem CRS; RFC 7946 separat | ? | ? | ? |

**Hinweis:** `?` bedeutet **noch nicht nachgewiesen**, nicht `nicht erfüllt`.

## 3. Kandidaten (noch keine Auswahl)

| Kandidat | Charakter / Prüfansatz | Ausgangsquelle |
|---|---|---|
| **QGIS-Desktop-Bordmittel** | Vorhandene Export-/Selektionsfunktionen bei Fachanwendern nutzen. | [Projekt-/Herstellerdokumentation](https://docs.qgis.org/3.44/en/docs/user_manual/) |
| **Vorhandene Viewer-/Dienstfunktionen** | Exportmöglichkeiten der späteren Webkomponenten gezielt verwenden. | [Projekt-/Herstellerdokumentation](https://docs.qwc.app/) |
| **Schlanker GDAL-/OGR-Auszug** | Nur bei Bedarf eigener abgesicherter Ablauf mit etabliertem GDAL/OGR-Backend. | [Projekt-/Herstellerdokumentation](https://gdal.org/en/stable/programs/ogr2ogr.html) |

## 4. Vergleichsmatrix

**Bewertung noch nicht begonnen:** Alle bisherigen Punkte- und Produktstandfelder waren `?` bzw. `n. a.`; eine ausgefüllte Matrix würde hier fälschlich eine belastbare Vergleichsstufe suggerieren. QGIS-/Viewer-Bordmittel und ein möglicher GDAL-Auszug sind **Lösungswege, noch keine ausgewählten Produkte**. Sicherheit und fachlich korrekte Formate haben Vorrang vor einer Punktzahl.

Sobald ein bestätigter Pilotbedarf eine echte Auswahl erforderlich macht, die [standardisierte Vergleichsmatrix](VORLAGE.md#4-vergleichsmatrix) nach [Methodik](BEWERTUNGSMETHODIK.md) mit aktuellem Produkt-/Versionsstand, nachgewiesenen Muss-Kriterien, Quellen und Bewertungsstichtag erstellen. **Keine Rangfolge oder Gesamtpunktzahl ohne Belege.**

## 5. Vor- und Nachteile – vorläufige Prüfhypothesen

**QGIS-Desktop-Bordmittel:** Keine zusätzliche Plattform nötig; für Gelegenheitsnutzer außerhalb QGIS kann der Ablauf zu technisch sein. **Noch zu verifizieren:** Bedienbarkeit, räumlicher Zuschnitt, Berechtigungen und reproduzierbarer Ablauf.

**Vorhandene Viewer-/Dienstfunktionen:** Direkter Export aus dem Browser kann bequem sein; Funktionsumfang und vor allem serverseitige Rechte müssen konkret geprüft werden. **Noch zu verifizieren:** Wird echter Zuschnitt angeboten? Wie werden Datei- und Direktaufrufe abgesichert?

**Schlanker GDAL-/OGR-Auszug:** Standardwerkzeuge ermöglichen wiederholbare Konvertierungen und Clipping; die sichere Web-/Job-Einbindung erzeugt zusätzlichen Entwicklungs- und Betriebsaufwand. **Noch zu verifizieren:** Auftragssteuerung, Rechtegrenzen, große Datensätze, Dateihandling und Testabdeckung.

## 6. Bewertung und Empfehlung

**Beschlossene Leitplanke:** A12 verlangt den berechtigten Auszug als Funktion, **keinen eigenen Serverdienst**. **Softwareauswahl weiterhin offen:** QGIS- und Viewer-/Dienst-Bordmittel haben Vorrang; falls sie die bestätigten Anforderungen nicht erfüllen, ist ein zusätzlicher Dienst begründet zu prüfen. Eine belastbare Produktempfehlung steht noch aus.

**Nächster Schritt:** In echten Pilotfällen **zuerst Datenbestände, Nutzerrollen und Zugriffspfade erheben** (Punkt 3, D). Danach vollständige Objektselektion und Clipping (auch über Freigabegrenzen), GeoJSON 2008 in EPSG:25832/25833/3068 sowie den RFC-7946-Sondermodus, DXF in repräsentativen CAD-Programmen und erforderliche Soldner-Transformationsverfahren mit Positiv-/Negativtests prüfen. Wenn ein Exportweg seine Rechte nicht wirksam durchsetzen kann, **nicht produktiv freischalten**.

## 7. Quellen und Stand

- [QGIS Benutzerhandbuch](https://docs.qgis.org/3.44/en/docs/user_manual/) – offizielle Dokumentation; vorhandene Auswahl-/Export-Funktionen
- [GDAL/OGR – ogr2ogr](https://gdal.org/en/stable/programs/ogr2ogr.html) – offizielle Dokumentation; Filter, räumlicher Zuschnitt, Konvertierung und CRS
- [RFC 7946 § 4 – Coordinate Reference System](https://www.rfc-editor.org/rfc/rfc7946#section-4) – WGS 84/CRS84 für standardkonformes GeoJSON
- [GDAL/OGR GeoJSON-Treiber](https://gdal.org/en/stable/drivers/vector/geojson.html) – klassisches GeoJSON 2008 vs. RFC-7946-Modus und CRS-Ausgabe
- [GDAL/OGR-DXF-Treiber](https://gdal.org/en/stable/drivers/vector/dxf.html) – DXF-Geometrien und Grenzen der Georeferenzierung
- [EPSG:3068 – DHDN / Soldner Berlin](https://epsg.io/3068) – CRS-Definition; erforderliche Transformation für die jeweiligen Einsatzgebiete prüfen
- [GDAL RFC 65 – GeoJSON RFC 7946](https://gdal.org/en/stable/development/rfc/rfc65_rfc7946_geojson.html) – konkrete Implementierung/Transformation bei GDAL-Ausgabe
- [QWC-Dokumentation](https://docs.qwc.app/) – offizielle Projektdoku; mögliche Webviewer-/Dienstintegrationen; Auswahl noch offen
- [VIC-GDI Entscheidung A12](../04_ENTSCHEIDUNGEN.md#a12) – intern; Fachgrenzen des Auszugs

**Quellenstand:** Ausgangslinks am 04.11.2026 zusammengestellt; **keine vollständige Release-, Lizenz-, Sicherheits- oder Praxistestprüfung**. Unabhängige Bewertungen und Erfahrungsberichte sowie ggf. PoC-Ergebnisse werden beim echten Vergleich mit Version und Datum ergänzt.
