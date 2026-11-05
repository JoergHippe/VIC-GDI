# Anforderungen an VIC-GDI

**Status:** Interner Arbeitsentwurf · fachliche Konkretisierung in den Piloten erforderlich.

## Fachliche Anforderungen

Die Tabelle beschreibt das Zielbild. Webkarten, Suche, [Geodatenauszug](ANHANG_A_GLOSSAR.md#extract) und mobile Arbeit (F05–F08) gehören zum ersten nutzbaren Stand, soweit ein priorisierter Pilotablauf sie benötigt. Die [Roadmap](07_ROADMAP.md#mvp-abgrenzung) führt den gemeinsamen Mindestumfang.

| ID | Anforderung | Bezug |
|---|---|---|
| F01 | Gemeinsame, fachbereichsneutrale [GDI](ANHANG_A_GLOSSAR.md#gdi) mit zunächst zwei Pilotbereichen | [A01](04_ENTSCHEIDUNGEN.md#a01), [A34](04_ENTSCHEIDUNGEN.md#a34) |
| F02 | Gemeinsame projektbezogene Daten nutzbar machen, ohne redundante führende Datenbestände | [A02–A09](04_ENTSCHEIDUNGEN.md#a02) |
| F03 | Projektidentität und schlanke Stammdaten; Projektgeometrie optional | [A06–A08](04_ENTSCHEIDUNGEN.md#a06) |
| F04 | [QGIS](ANHANG_A_GLOSSAR.md#qgis) Desktop mit zentralen Ressourcen, aber eigenständigen Fachprojekten | [A04](04_ENTSCHEIDUNGEN.md#a04), [A17](04_ENTSCHEIDUNGEN.md#a17) |
| F05 | Webkarten für Gelegenheitsnutzer mit einfacher und erweiterter Sicht | [A10](04_ENTSCHEIDUNGEN.md#a10), [A11](04_ENTSCHEIDUNGEN.md#a11), [A18](04_ENTSCHEIDUNGEN.md#a18), [A19](04_ENTSCHEIDUNGEN.md#a19) |
| F06 | Suche nach Projekten, Orten/Adressen und ausgewählten Objekten | [A20](04_ENTSCHEIDUNGEN.md#a20) |
| F07 | Berechtigter Geodatenauszug **als Funktion**, zunächst mit vorhandenen Werkzeugen: vollständige Objektselektion, optional Clipping; GPKG, klassisches GeoJSON, DXF und CSV, optional Shapefile; Quell-/Ziel-CRS einschließlich EPSG:3068. RFC 7946 nur Sondermodus; Rechteausgestaltung offen. Technische Details in [SW-06](software/06_GEODATENAUSZUG.md). | [A12](04_ENTSCHEIDUNGEN.md#a12), [A21](04_ENTSCHEIDUNGEN.md#a21), [A26](04_ENTSCHEIDUNGEN.md#a26) |
| F08 | Mobile Online-/Offline-Arbeit mit erprobten Werkzeugen | [A13](04_ENTSCHEIDUNGEN.md#a13) |
| F09 | Amtliche Basisdaten bevorzugt über Dienste; dokumentierte Stände bei Bedarf | [A05](04_ENTSCHEIDUNGEN.md#a05), [A22](04_ENTSCHEIDUNGEN.md#a22) |
| F10 | Geodatenquellen, Aktualität, Herkunft und Nutzungseinschränkungen nachvollziehen | [A15](04_ENTSCHEIDUNGEN.md#a15) |
| F11 | Selektive Migration; ungeeignete synchronisierte [GIS](ANHANG_A_GLOSSAR.md#gis)-Arbeitsdatenhaltung ablösen | [A36](04_ENTSCHEIDUNGEN.md#a36) |
| F12 | Schrittweise fachliche Pilotfunktionen und nach Nutzen priorisierter [MVP](ANHANG_A_GLOSSAR.md#mvp) | [A34](04_ENTSCHEIDUNGEN.md#a34), [A35](04_ENTSCHEIDUNGEN.md#a35) |

## Nichtfunktionale Anforderungen

- **Sicherheit:** Bestehende Unternehmensidentitäten und serverseitig durchgesetzte Zugriffsrechte; IT-Abstimmung offen ([A09](04_ENTSCHEIDUNGEN.md#a09), [A25](04_ENTSCHEIDUNGEN.md#a25), [A26](04_ENTSCHEIDUNGEN.md#a26)).
- **Betrieb:** Test/Produktion getrennt, Backups, Wiederherstellbarkeit, Monitoring ([A27–A29](04_ENTSCHEIDUNGEN.md#a27)).
- **Wartbarkeit:** [Git](ANHANG_A_GLOSSAR.md#git) für geeignete Konfigurationen, Skripte, [QML](ANHANG_A_GLOSSAR.md#qml) und Migrationen; keine produktiven [Geodaten](ANHANG_A_GLOSSAR.md#geodaten) in Git ([A30](04_ENTSCHEIDUNGEN.md#a30)).
- **Bedienbarkeit:** Desktop/Tablet und vereinfachte Kartenansichten; mobile Nutzung nach Anwendungsfall ([A13](04_ENTSCHEIDUNGEN.md#a13), [A19](04_ENTSCHEIDUNGEN.md#a19)).
- **Interoperabilität:** QGIS, [PostGIS](ANHANG_A_GLOSSAR.md#postgis), etablierte GIS-Dienste und offene Austauschformate ([A10–A12](04_ENTSCHEIDUNGEN.md#a10)).
- **Koordinatenbezug:** ETRS89/[UTM](ANHANG_A_GLOSSAR.md#utm) EPSG:25832/25833 bevorzugt; **DHDN / Soldner Berlin (EPSG:3068)** ausdrücklich berücksichtigen; weitere lokale Systeme und Höhenbezüge nach Geografie und Genauigkeit prüfen ([A21](04_ENTSCHEIDUNGEN.md#a21)).
- **Datenintegrität:** Grundlegende konsistente Datenhaltung ist Pflicht; **zusätzliche fachliche DB-/QGIS-Validierungsregeln** sind nach [A38](04_ENTSCHEIDUNGEN.md#a38) noch nicht beschlossen.
- **Wirtschaftlichkeit:** Gezielter Wissensaufbau mit eingeplanten Ressourcen; keine pauschale Zertifizierungspflicht ([A33](04_ENTSCHEIDUNGEN.md#a33)).

## Noch zu spezifizieren

Konkrete Anwendungsfälle, Datensätze, Datenmengen pro Pilot, Rollenmatrix, Akzeptanzkriterien, Bedienabläufe, Qualitätsanforderungen und Abhängigkeiten werden vor der jeweiligen Umsetzung erarbeitet. Diese Tabelle ersetzt kein abgenommenes Lastenheft.
