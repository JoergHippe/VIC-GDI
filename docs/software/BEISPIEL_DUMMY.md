# Mustervergleich (DUMMY) – fiktiver Kartenserver

**WICHTIG: Dies ist ausschließlich eine Darstellungsvorlage. Alle drei Produkte, Versionen, Veröffentlichungsdaten, Entwicklungsaktivitäten, Bewertungen, Prüfergebnisse und Kostenannahmen sind frei erfunden.** Keine Bewertung existierender Kartenserver; keine Technologie- oder Architekturentscheidung.

## 1. Zweck und Abgrenzung

Ein Kartenserver veröffentlicht freigegebene Geodaten und Karten für Webviewer bzw. andere GIS-Clients. Im VIC-Kontext wären QGIS-Projekte, PostGIS und abgesicherte interne Zugriffe wichtige Prüfgegenstände. Der Webviewer ist eine **andere** Softwarekategorie.

## 2. Besondere Anforderungen

- **Muss (Demo):** WMS-Dienst aus freigegebenen Karten bereitstellen.
- **Muss (Demo):** Zugriffsschutz auch bei direktem Aufruf des Dienst-Endpunkts.
- **Soll (Demo):** QGIS-Symbologie möglichst ohne parallele manuelle Pflege übernehmen.
- **Noch zu klären:** Tatsächliche Pilotkarten, Nutzerzahlen, Rechte, Leistung und IT-Betriebsstandard.

| Muss-Kriterium | Atlas (fiktiv) | Brücke (fiktiv) | Fokus (fiktiv) |
|---|---|---|---|
| WMS-Dienst | erfüllt* | erfüllt* | erfüllt* |
| Serverseitiger Zugriffsschutz | erfüllt* | erfüllt* | erfüllt* |

*Ergebnisse ausschließlich erfunden, um die Formatierung zu demonstrieren.*

## 3. Kandidaten

| Kandidat | Fiktives Profil | Lizenz-/Kostenannahme (erfunden) | Einordnung |
|---|---|---|---|
| **Atlas** | Enger QGIS-/Projektbezug, moderater Betriebsaufwand | Open Source, kein Lizenzpreis | Beispiel für Integration |
| **Brücke** | Vielseitig und funktionsreich, mehr Konfiguration | Open Source, optionale Leistungen | Beispiel für Funktionsbreite |
| **Fokus** | Schlanke Kartenbereitstellung, begrenzte Zusatzfunktionen | Open Source, kein Lizenzpreis | Beispiel für Minimalismus |

## 4. Vergleichsmatrix – Werte vollständig erfunden

Bewertungsskala `0–3`; `3` = sehr passend. Gewichte entsprechen der [Methodik](BEWERTUNGSMETHODIK.md). **Fiktiver Bewertungsstichtag: 04.11.2026.** Die drei zusätzlichen Zeilen sind Sachangaben, keine Punktekriterien.

| Kriterium (Gewicht) | Atlas | Brücke | Fokus |
|---|---:|---:|---:|
| **Erstveröffentlichung / seit (Jahr)** | 2012 (erfunden) | 2007 (erfunden) | 2020 (erfunden) |
| **Aktuelle stabile Version (Releasedatum)** | 4.2.1 (15.10.2026; erfunden) | 7.1.0 (05.09.2026; erfunden) | 1.9.0 (25.06.2025; erfunden) |
| **Entwicklungsaktivität (12 Monate)** | 4 stabile Releases, aktiv (erfunden) | 2 stabile Releases, kontinuierlich (erfunden) | 0 stabile Releases, geringer Release-Takt (erfunden) |
| Fachliche/funktionale Eignung (30 %) | 3 | 2 | 2 |
| Integration/Interoperabilität (20 %) | 3 | 2 | 1 |
| Sicherheit/Berechtigungen (15 %) | 2 | 3 | 1 |
| Betrieb/Wartbarkeit (15 %) | 2 | 1 | 3 |
| Reife/Zukunftsfähigkeit (10 %) | 2 | 3 | 2 |
| Kosten/Lizenzen (10 %) | 3 | 2 | 3 |
| **Demo-Gesamt (0–100 Punkte)** | **86,7** | **70,0** | **63,3** |
| **Evidenzstand** | E0 (fiktiv) | E0 (fiktiv) | E0 (fiktiv) |

*Die frei erfundenen Releasezahlen zeigen lediglich die gewünschte Darstellungsform. Weniger Releases bedeuten nicht automatisch schlechtere Software; Wartungsqualität, Sicherheitsfixes und Projektentwicklung sind separat zu beurteilen.*

*Beispielrechnung Atlas: `(30×3 + 20×3 + 15×2 + 15×2 + 10×2 + 10×3) / 3 = 86,7`. In echten Bewertungen wäre bei Evidenz E0 und unbekannten Sachverhalten keine belastbare Rangliste zulässig. Die Zahlen illustrieren nur das Layout.*

## 5. Stärken und Schwächen – rein hypothetisch

**Atlas:** Vorteil wäre die enge Integration in bestehende QGIS-Projektabläufe und die geringe Doppelerfassung von Styles. Nachteil könnte ein engerer Zuschnitt auf genau dieses Ökosystem sein; Rechte und Releasepflege müssten getestet werden.

**Brücke:** Vorteil wäre ein breites Dienst- und Formatangebot, falls mehrere voneinander unabhängige GIS-Quellen eingebunden werden. Nachteil könnte zusätzlicher Konfigurations-, Sicherheits- und Betriebsaufwand sein, der für die Piloten nicht gerechtfertigt ist.

**Fokus:** Vorteil wäre eine überschaubare, möglicherweise gut wartbare Kartenbereitstellung. Nachteil könnte sein, dass für QGIS-Projekte oder komplexe Benutzerrechte zusätzliche Werkzeuge und Pflegeprozesse nötig werden.

## 6. Bewertung und Empfehlung – rein hypothetisch

**Fiktive Empfehlung:** „Atlas“ zunächst als Pilotkandidat testen, weil im erfundenen Szenario die Projektnähe den größten Nutzen bringt. „Brücke“ als Alternative, wenn zusätzliche Dienste tatsächlich benötigt werden. „Fokus“ nur, wenn die Minimalanforderungen dominieren.

**So soll ein echter Beschluss vorbereitet werden:** Vorher konkrete Pilotkarten, aktuelle Produktversionen, OGC-Funktionen, Rechteprüfung bis zum Endpunkt, Update-/Restore-Weg und benötigte IT-Ressourcen nachweisen. Ein knappes Testergebnis ist wertvoller als eine scheinbar exakte Punktzahl ohne Tests.

## 7. Quellen: Demonstration der gewünschten Linkarten

**Die folgenden realen Quellen dienen ausschließlich als Beispiel einer späteren Recherche, nicht als Beleg für die erfundenen Kandidaten oder Bewertungen:**

| Belegart | Beispiel | Für eine echte Bewertung heranziehen |
|---|---|---|
| Offizielle Produktdokumentation | [QGIS: QGIS Server](https://www.qgis.org/project/overview/) | Offiziell unterstützte Dienste und Veröffentlichung von QGIS-Projekten |
| Offizielle technische Dokumentation | [GeoServer User Manual](https://docs.geoserver.org/main/en/user/introduction/overview/) | Komponenten, unterstützte Schnittstellen, Administrationsanforderungen |
| Externes Projektprofil | [GeoServer bei OSGeo](https://www.osgeo.org/projects/geoserver/) | Unabhängiger Kontext, Projektgemeinschaft und weiterführende Links |
| Entwicklungs-/Feedbackquelle | [GeoServer-Projekt](https://github.com/geoserver/geoserver) | Aktuelle Issues, Releases, Sicherheits- und Wartungsaktivität |
| Eigener Praxistest | Noch nicht vorhanden | Konfiguration, Testdaten, Befund, Datum und Wiederholungsschritte |

**Quellenstand des Musters:** 04.11.2026; keine vollständige Produktprüfung. Für reale Vergleiche externe Erfahrungen und Reviews kritisch nach Aktualität, Version, Unabhängigkeit und Übertragbarkeit prüfen.
