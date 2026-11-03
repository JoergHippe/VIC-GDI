# Anforderungen an VIC-GDI

**Status:** Interner Arbeitsentwurf · fachliche Konkretisierung in den Piloten erforderlich.

## Fachliche Anforderungen

Die Tabelle beschreibt das Zielbild. Webkarten, Suche, Geodatenauszug und mobile Arbeit (F05–F08) gehören zum ersten nutzbaren Stand, soweit ein priorisierter Pilotablauf sie benötigt. Die [Roadmap](06_ROADMAP.md#mvp-abgrenzung) führt den gemeinsamen Mindestumfang.

| ID | Anforderung | Bezug |
|---|---|---|
| F01 | Gemeinsame, fachbereichsneutrale GDI mit zunächst zwei Pilotbereichen | A01, A34 |
| F02 | Gemeinsame projektbezogene Daten nutzbar machen, ohne redundante führende Datenbestände | A02–A09 |
| F03 | Projektidentität und schlanke Stammdaten; Projektgeometrie optional | A06–A08 |
| F04 | [QGIS](ANHANG_A_GLOSSAR.md#qgis) Desktop mit zentralen Ressourcen, aber eigenständigen Fachprojekten | A04, A17 |
| F05 | Webkarten für Gelegenheitsnutzer mit einfacher und erweiterter Sicht | A10, A11, A18, A19 |
| F06 | Suche nach Projekten, Orten/Adressen und ausgewählten Objekten | A20 |
| F07 | Berechtigter Geodatenauszug in geeigneten Formaten und Raumbezügen | A12 |
| F08 | Mobile Online-/Offline-Arbeit mit erprobten Werkzeugen | A13 |
| F09 | Amtliche Basisdaten bevorzugt über Dienste; dokumentierte Stände bei Bedarf | A05, A22 |
| F10 | Geodatenquellen, Aktualität, Herkunft und Nutzungseinschränkungen nachvollziehen | A15 |
| F11 | Selektive Migration; ungeeignete synchronisierte GIS-Arbeitsdatenhaltung ablösen | A36 |
| F12 | Schrittweise fachliche Pilotfunktionen und nach Nutzen priorisierter [MVP](ANHANG_A_GLOSSAR.md#mvp) | A34, A35 |

## Nichtfunktionale Anforderungen

- **Sicherheit:** Bestehende Unternehmensidentitäten und serverseitig durchgesetzte Zugriffsrechte; IT-Abstimmung offen (A09, A25, A26).
- **Betrieb:** Test/Produktion getrennt, Backups, Wiederherstellbarkeit, Monitoring (A27–A29).
- **Wartbarkeit:** [Git](ANHANG_A_GLOSSAR.md#git) für geeignete Konfigurationen, Skripte, QML und Migrationen; keine produktiven Geodaten in Git (A30).
- **Bedienbarkeit:** Desktop/Tablet und vereinfachte Kartenansichten; mobile Nutzung nach Anwendungsfall (A13, A19).
- **Interoperabilität:** QGIS, [PostGIS](ANHANG_A_GLOSSAR.md#postgis), etablierte GIS-Dienste und offene Austauschformate (A10–A12).
- **Koordinatenbezug:** ETRS89/UTM32 oder UTM33 bevorzugt nach Geografie, Ausnahmen und Höhenbezug berücksichtigen (A21).
- **Datenintegrität:** Fachlich eindeutige Datenmodelle; konkrete Durchsetzung von DB-Regeln ist noch nicht beschlossen (A38).
- **Wirtschaftlichkeit:** Gezielter Wissensaufbau mit eingeplanten Ressourcen; keine pauschale Zertifizierungspflicht (A33).

## Noch zu spezifizieren

Konkrete Anwendungsfälle, Datensätze, Datenmengen pro Pilot, Rollenmatrix, Akzeptanzkriterien, Bedienabläufe, Qualitätsanforderungen und Abhängigkeiten werden vor der jeweiligen Umsetzung erarbeitet. Diese Tabelle ersetzt kein abgenommenes Lastenheft.
