# Projektkonzept VIC-GDI

**Status:** Interner Arbeitsentwurf · fachliche Initiative des GIS-Teams und beteiligter Fachkollegen; Umsetzungs-, Budget- und Betriebsfreigabe durch GF/IT noch offen.

## Ausgangslage

[Geodaten](ANHANG_A_GLOSSAR.md#geodaten) und [QGIS](ANHANG_A_GLOSSAR.md#qgis)-Projekte werden in unterschiedlichen Fachbereichen und Speicherorten verwaltet. Gemeinsame Datennutzung, einheitliche Bereitstellung und kontrollierter Betrieb sollen verbessert werden. In der Baubetreuung werden QGIS-Arbeitsbestände teilweise über synchronisierte SharePoint-/OneDrive-Verzeichnisse genutzt; diese Arbeitsweise soll für führende [GIS](ANHANG_A_GLOSSAR.md#gis)-Arbeitsdaten kontrolliert abgelöst werden ([A36](04_ENTSCHEIDUNGEN.md#a36)).

## Warum wir VIC-GDI einführen wollen

Die heutige Arbeit mit Geodaten verteilt sich auf Fachbereiche, Projekte und unterschiedliche Speicherorte. Gemeinsame Bestände sind dadurch nicht immer unmittelbar auffindbar; Daten können mehrfach kopiert und unabhängig fortgeschrieben werden. Das erhöht den Abstimmungsaufwand und das Risiko voneinander abweichender Datenstände. In der Baubetreuung werden GIS-Arbeitsbestände teilweise über synchronisierte SharePoint-/OneDrive-Verzeichnisse genutzt; diese Arbeitsweise soll für führende Arbeitsdaten kontrolliert abgelöst werden. **Die Initiative zur Verbesserung geht vom GIS-Team und beteiligten Fachkollegen aus.** Die Bestandsaufnahme mit den Pilotbereichen dient der Priorisierung und passgenauen Einführung, nicht der Grundsatzprüfung, ob eine GDI Vorteile bietet.

Die geplante [Geodateninfrastruktur](ANHANG_A_GLOSSAR.md#gdi) soll **nicht bloß neue Server bereitstellen**, sondern eine gemeinsame, verlässliche Arbeitsgrundlage organisieren: Wo liegt ein führender Datenbestand? Wer verantwortet und pflegt ihn? Wie greifen andere Berechtigte auf denselben freigegebenen Stand zu? Wie können QGIS-Fachanwender, gelegentliche Kartennutzer und mobile Teams aufgabenbezogen arbeiten? Die GDI **ergänzt** vorhandene CAD-, BIM-, M365- und Fachsysteme; sie ersetzt sie nicht.

### Heutige Herausforderungen und angestrebte Verbesserung

| Heutige Herausforderung | Angestrebte Verbesserung durch VIC-GDI |
|---|---|
| Daten, QGIS-Projekte und Zuständigkeiten verteilen sich auf verschiedene Ablagen. | Nachvollziehbare Quellen, klare Datenhoheit und verlässliche Zugriffswege. |
| Geeignete Bestände werden zwischen Projekten kopiert und ggf. unterschiedlich weitergeführt. | Gemeinsame Nutzung führender Daten statt unnötiger unabhängiger Kopien. |
| Herkunft, Aktualität oder Freigabestand sind nicht immer unmittelbar erkennbar. | Verantwortliche und relevante Datenstände nachvollziehbar machen. |
| Gelegentliche Kartenfragen erfordern teilweise GIS-Unterstützung. | Bei Bedarf einfache, berechtigungsgesteuerte Webkarten für Nicht-Spezialisten. |
| Mobile Erfassungen müssen in den fachlich geprüften Bestand übernommen werden. | Übertragung, fachliche Prüfung und Freigabe klar unterscheiden. |
| Wiederkehrende Konfigurationen und Betriebswissen sind uneinheitlich verteilt. | Gemeinsame Ressourcen und dokumentierte, vertretbare Abläufe. |

### Zielprinzip auf einen Blick

```mermaid
flowchart LR
  A["Projekt A: eigene Datenkopie"] --> X["Heute: mehrere Arbeitsstände"]
  B["Projekt B: eigene Datenkopie"] --> X
  X -.->|Für geeignete gemeinsame Daten| D["Ziel: ein führender, fachlich verantworteter Bestand"]
  D --> Q["QGIS-Facharbeitsplätze"]
  D --> W["Freigegebene Webkarten bei Bedarf"]
  M["Mobile Erfassung"] --> P["Fachliche Prüfung"]
  P --> D
```

**Einordnung:** Das Diagramm illustriert ein Zielprinzip, keinen nachgewiesenen heutigen Ablauf und keine Pflicht, sämtliche QGIS-Projekte, Raster- oder CAD-Dateien in PostGIS zu speichern. Der mobile Datenweg und die Webbereitstellung sind pilotabhängig.

### Was das im Arbeitsalltag bedeuten kann

- **Baubetreuung:** Ein mobil erfasster Leitungsverlauf wird übertragen, geprüft und – nur bei fachlicher Eignung – in einen führenden Bestand übernommen. Die Synchronisation ist keine automatische Freigabe ([BB-01](05_PILOTKONKRETISIERUNG.md#bb-01)).
- **Verkehrsanlagenplanung:** Zwei Planungsprojekte verwenden einen geeigneten gemeinsamen Geodatenbestand, anstatt eigene Kopien mit möglicherweise verschiedenen Aktualisierungsständen zu pflegen.
- **Gelegentliche Kartennutzung:** Wer kein QGIS benötigt, kann bei entsprechendem Pilotbedarf freigegebene Karten im Browser einsehen, ohne die führenden Daten verändern zu können.

### Nutzen der GDI erschließen und die Einführung gezielt gestalten

Eine gemeinsame Geodateninfrastruktur bietet gegenüber einer dezentralen, teils redundanten Ablage **klare strukturelle Vorteile**: geeignete Datenbestände können an einer verantwortlichen Stelle gepflegt, berechtigt gemeinsam genutzt und in verschiedenen Fachabläufen wiederverwendet werden. **Fachlich** verbessert das die Grundlage für aktuelle, nachvollziehbare Datenstände; **organisatorisch** reduziert es unnötige Kopier- und Abstimmungswege; **technisch** ermöglicht es standardisierte, wartbare Zugriffs- und Bereitstellungswege.

**Die Piloten sind erste Schritte der GDI-Einführung und keine Experimente zur grundsätzlichen Sinnhaftigkeit.** Mit ihnen werden relevante Arbeitsabläufe priorisiert, Datenmodelle und Schnittstellen abgestimmt, Funktionen eingeführt und die Betriebsfähigkeit überprüft. Fachliche Abnahme und geeignete Vergleichsgrößen zeigen anschließend, **wie gut** die Vorteile im jeweiligen Ablauf realisiert wurden. Quantifizierte Zeit- oder Kosteneinsparungen werden ohne belastbare Ausgangsdaten nicht versprochen. Aufwand und laufender Betrieb sind für die **konkreten Umsetzungsvarianten** verantwortlich zu planen; dies stellt die strategische Zielsetzung nicht infrage.

## Ziele

- Fachbereichsneutrale, interne [Geodateninfrastruktur](ANHANG_A_GLOSSAR.md#gdi).
- Schrittweise ausbaubar und erweiterbar.
- Verlässliche gemeinsame Datenhaltung mit eindeutiger fachlicher Zuständigkeit.
- QGIS Desktop als zentraler Fachclient; einfache Webkarten für Gelegenheitsnutzer; geeignete mobile Workflows.
- Sichere Nutzung im Unternehmensnetz bzw. über [VPN](ANHANG_A_GLOSSAR.md#vpn); kontrollierte externe Zusammenarbeit bei Bedarf.
- Möglichst Standardtechnologien statt eigener GIS-Basisentwicklungen.
- Beherrschbarer Einführungs-, Betriebs- und Schulungsaufwand.

## Pilotbereiche

1. **Baubetreuung:** räumlich bezogene Vorgänge, Karten, geeignete mobile Arbeitsabläufe.
2. **Verkehrsanlagenplanung:** projektbezogene und gemeinsam genutzte Geodaten, QGIS-Arbeitsabläufe.

Diese Pilotbereiche bilden die ersten **praktischen Einführungsschritte**. Sie dürfen unterschiedliche fachliche Anforderungen und Einführungszeitpunkte haben; ein identischer Funktionsumfang ist nicht erforderlich ([A34](04_ENTSCHEIDUNGEN.md#a34)).

## Abgrenzung

- Kein öffentliches anonymes GIS-Portal als primäres Ziel.
- Die GDI ergänzt [CAD](ANHANG_A_GLOSSAR.md#cad)-, [BIM](ANHANG_A_GLOSSAR.md#bim)-, M365- und Fachanwendungen um eine gemeinsame Geodatenbasis.
- Keine vollständige Migration aller Dateiformate nach [PostGIS](ANHANG_A_GLOSSAR.md#postgis).
- Keine Eigenentwicklung eines Offline-Synchronisationssystems.
- Kein umfassendes formales Qualitätsmanagement für amtliche Geobasisdaten.
- Kein umfangreiches [ITSM](ANHANG_A_GLOSSAR.md#itsm)-, [CI/CD](ANHANG_A_GLOSSAR.md#ci-cd)- oder [HA](ANHANG_A_GLOSSAR.md#ha)-System ohne nachgewiesenen Bedarf.

## Prinzipien

Bedarf vor Technik; Datenhoheit; nachvollziehbare Änderungen; Standard vor Sonderlösung; schrittweise Einführung; zentrale Bereitstellung ohne unnötige Kopien. Verbindliche Details siehe [Entscheidungen](04_ENTSCHEIDUNGEN.md), technische Umsetzung siehe [Architektur](03_ARCHITEKTUR.md).
