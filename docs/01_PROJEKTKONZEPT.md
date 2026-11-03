# Projektkonzept VIC-GDI

**Status:** Interner Arbeitsentwurf

## Ausgangslage

Geodaten und [QGIS](ANHANG_A_GLOSSAR.md#qgis)-Projekte werden in unterschiedlichen Fachbereichen und Speicherorten verwaltet. Gemeinsame Datennutzung, einheitliche Bereitstellung und kontrollierter Betrieb sollen verbessert werden. In der Baubetreuung werden QGIS-Arbeitsbestände teilweise über synchronisierte [SharePoint](ANHANG_A_GLOSSAR.md#sharepoint)-/[OneDrive](ANHANG_A_GLOSSAR.md#onedrive)-Verzeichnisse genutzt; diese Arbeitsweise soll für führende [GIS](ANHANG_A_GLOSSAR.md#gis)-Arbeitsdaten kontrolliert abgelöst werden ([A36](04_ENTSCHEIDUNGEN.md#a36)).

## Ziele

- Fachbereichsneutrale, schrittweise ausbaubare interne [Geodateninfrastruktur](ANHANG_A_GLOSSAR.md#gdi).
- Verlässliche gemeinsame Datenhaltung mit eindeutiger fachlicher Zuständigkeit.
- QGIS Desktop als zentraler Fachclient; einfache Webkarten für Gelegenheitsnutzer; geeignete mobile Workflows.
- Sichere Nutzung im Unternehmensnetz bzw. über [VPN](ANHANG_A_GLOSSAR.md#vpn); kontrollierte externe Zusammenarbeit bei Bedarf.
- Möglichst Standardtechnologien statt eigener GIS-Basisentwicklungen.
- Beherrschbarer Einführungs-, Betriebs- und Schulungsaufwand.

## Pilotbereiche

1. **Baubetreuung/Bauüberwachung:** räumlich bezogene Vorgänge, Karten, geeignete mobile Arbeitsabläufe.
2. **Verkehrsanlagenplanung:** projektbezogene und gemeinsam genutzte Geodaten, QGIS-Arbeitsabläufe.

Die Piloten sind unterschiedlich und müssen nicht zeitgleich denselben Funktionsumfang erreichen ([A34](04_ENTSCHEIDUNGEN.md#a34)).

## Abgrenzung

- Kein öffentliches anonymes GIS-Portal als primäres Ziel.
- Die GDI ergänzt CAD-, BIM-, M365- und Fachanwendungen um eine gemeinsame Geodatenbasis.
- Keine vollständige Migration aller Dateiformate nach [PostGIS](ANHANG_A_GLOSSAR.md#postgis).
- Keine Eigenentwicklung eines Offline-Synchronisationssystems.
- Kein umfassendes formales Qualitätsmanagement für amtliche Geobasisdaten.
- Kein umfangreiches ITSM-, [CI/CD](ANHANG_A_GLOSSAR.md#ci-cd)- oder [HA](ANHANG_A_GLOSSAR.md#ha)-System ohne nachgewiesenen Bedarf.

## Prinzipien

Bedarf vor Technik; Datenhoheit; nachvollziehbare Änderungen; Standard vor Sonderlösung; schrittweise Einführung; zentrale Bereitstellung ohne unnötige Kopien. Verbindliche Details siehe [Entscheidungen](04_ENTSCHEIDUNGEN.md), technische Umsetzung siehe [Architektur](03_ARCHITEKTUR.md).
