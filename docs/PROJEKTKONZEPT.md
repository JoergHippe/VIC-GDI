# Projektkonzept VIC-GDI

**Status:** Interner Arbeitsentwurf · 2026-11-03

## Ausgangslage

Geodaten und QGIS-Projekte werden in unterschiedlichen Fachbereichen und Speicherorten verwaltet. Gemeinsame Datennutzung, einheitliche Bereitstellung und kontrollierter Betrieb sollen verbessert werden. In der Baubetreuung werden QGIS-Arbeitsbestände teilweise über synchronisierte SharePoint-/OneDrive-Verzeichnisse genutzt; diese Arbeitsweise soll für führende GIS-Arbeitsdaten kontrolliert abgelöst werden (A36).

## Ziele

- Fachbereichsneutrale, schrittweise ausbaubare interne Geodateninfrastruktur.
- Verlässliche gemeinsame Datenhaltung mit eindeutiger fachlicher Zuständigkeit.
- QGIS Desktop als zentraler Fachclient; einfache Webkarten für Gelegenheitsnutzer; geeignete mobile Workflows.
- Sichere Nutzung im Unternehmensnetz bzw. über VPN; kontrollierte externe Zusammenarbeit bei Bedarf.
- Möglichst Standardtechnologien statt eigener GIS-Basisentwicklungen.
- Beherrschbarer Einführungs-, Betriebs- und Schulungsaufwand.

## Pilotbereiche

1. **Baubetreuung/Bauüberwachung:** räumlich bezogene Vorgänge, Karten, geeignete mobile Arbeitsabläufe.
2. **Verkehrsanlagenplanung:** projektbezogene und gemeinsam genutzte Geodaten, QGIS-Arbeitsabläufe.

Die Piloten sind unterschiedlich und müssen nicht zeitgleich denselben Funktionsumfang erreichen (A34).

## Abgrenzung

- Kein öffentliches anonymes GIS-Portal als primäres Ziel.
- Kein Ersatz für CAD-, BIM- oder Fachanwendungen.
- Keine vollständige Migration aller Dateiformate nach PostGIS.
- Keine Eigenentwicklung eines Offline-Synchronisationssystems.
- Kein umfassendes formales Qualitätsmanagement für amtliche Geobasisdaten.
- Kein umfangreiches ITSM-, CI/CD- oder HA-System ohne nachgewiesenen Bedarf.

## Prinzipien

Bedarf vor Technik; Datenhoheit; nachvollziehbare Änderungen; Standard vor Sonderlösung; schrittweise Einführung; zentrale Bereitstellung ohne unnötige Kopien. Verbindliche Details siehe [Entscheidungen](ENTSCHEIDUNGEN.md), technische Umsetzung siehe [Architektur](ARCHITEKTUR.md).
