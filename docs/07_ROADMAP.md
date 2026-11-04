# Roadmap und Einführung

**Status:** Interner Arbeitsentwurf · keine Termin-, Budget- oder Personalzusage.

Die [Pilotkonkretisierung](05_PILOTKONKRETISIERUNG.md) trennt fachlich benannte Tätigkeiten und bestehende mobile Praxis der Baubetreuung von Ablaufvorschlägen und offenen Fragen. Die Auswahl und Abnahme der ersten Pilotabläufe stehen aus.

## Vorgehensprinzip

Gemeinsame, schlanke [GDI](ANHANG_A_GLOSSAR.md#gdi)-Basis und zwei früh beteiligte Pilotbereiche ([A34](04_ENTSCHEIDUNGEN.md#a34)). Der [MVP](ANHANG_A_GLOSSAR.md#mvp) ist priorisiert und anpassbar; gemeinsamer GDI-MVP und fachliche Pilot-MVPs werden getrennt geplant ([A35](04_ENTSCHEIDUNGEN.md#a35)). Phasen dürfen sich überlappen.

### Ablauf bis zur belastbaren Pilotentscheidung

```mermaid
flowchart LR
  Prepare["IT und Geschäftsführung abstimmen, Ist-Abläufe erheben"]
  Select["Pilotfälle und Prüfumfang festlegen"]
  Release["Erprobung gesondert freigeben"]
  Test["Offene Machbarkeit gezielt prüfen"]
  Decide{"Pilot freigeben?"}
  Use["Pilot umsetzen"]
  Prepare --> Select
  Select -->|Machbarkeit offen| Release
  Release --> Test --> Decide
  Select -->|Machbarkeit ausreichend geklärt| Decide
  Decide -->|Ja| Use
  Decide -->|Überarbeiten| Select
```

Aktuell laufen Vorbereitung und Abstimmung. IT klärt den Betriebsrahmen, die Geschäftsführung entscheidet über Ressourcen für die Vorbereitung. Praktische Erprobung folgt nach gesonderter Freigabe. Über Umfang, Budget und Start der Piloten entscheidet die Geschäftsführung anhand der Ergebnisse und des mit IT geklärten Betriebsrahmens. Siehe [Mindestabnahme für den Betrieb](BRIEFING_IT.md#mindestabnahme-vor-produktivem-pilot) und [Folgeentscheidung der Geschäftsführung](BRIEFING_GESCHAEFTSFUEHRUNG.md#folgeentscheidung).

## Etappen

### 0 – Vorbereitung und Bestandsaufnahme
- IT, [GIS](ANHANG_A_GLOSSAR.md#gis)-Team und Pilotbereiche abstimmen; Zuständigkeiten skizzieren.
- Bestehende [QGIS](ANHANG_A_GLOSSAR.md#qgis)-Projekte, Datenquellen, Speicherorte und kritische Abläufe erfassen.
- Problematische synchronisierte SharePoint-/OneDrive-GIS-Arbeitsdatenhaltung in der Baubetreuung identifizieren.
- Konkrete Pilot-Use-Cases und Minimalerfolgskriterien festlegen.
- Wissens- und Schulungsbedarf samt Kapazitäten einplanen ([A33](04_ENTSCHEIDUNGEN.md#a33)).
- [Modelle für Umsetzung, Qualifizierung und dauerhaften Betrieb](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md) (intern/gemeinsam/extern, D1–D3) anhand interner Kompetenzen und Ressourcen mit GIS/IT bewerten; **Entscheidung [A39](04_ENTSCHEIDUNGEN.md#a39) durch GF und IT offen**, vor produktivem Pilotbetrieb verbindlich klären.

### 1 – Gemeinsame technische Basis
- [PostGIS](ANHANG_A_GLOSSAR.md#postgis) und QGIS-Desktop-Anbindung; geeignete gemeinsame Datenmodelle.
- TEST/PROD, Grundrechte, Sicherung und Basisüberwachung mit IT abstimmen.
- [Git](ANHANG_A_GLOSSAR.md#git)-basierte Ressourcen und kontrollierte Änderungen etablieren.

### 2 – Erste nutzbare Pilotfunktionen
- **BB:** ausgewählte räumliche Arbeitsabläufe und, wo erforderlich, mobile Nutzung.
- Einfache Karten über den geprüften Standard-[Webviewer](ANHANG_A_GLOSSAR.md#webviewer) bereitstellen, sofern der ausgewählte Ablauf sie braucht.
- **Verkehrsanlagenplanung:** gemeinsame Geodaten, Projektbezug und QGIS-Workflows.
- Fachliche Abnahme an realen Daten; keine Pflicht zu gleichem Funktionsumfang.

### 3 – Stabilisierung und kontrollierte Migration
- OneDrive-/SharePoint-basierte führende GIS-Arbeitsbestände der BB nach [A36](04_ENTSCHEIDUNGEN.md#a36) kontrolliert ablösen.
- Datenquellen, Mehrbenutzerbearbeitung, Datenhoheit und Berechtigungen testen.
- Betriebs-, Schulungs- und Supportaufwand aus der Praxis erfassen.

### 4 – Review und Ausbau
- Nutzen, Bedienbarkeit, Datenqualität, Wartbarkeit, Ressourcen und Akzeptanz bewerten.
- Architektur bei Bedarf korrigieren, offene Entscheidungen gezielt bearbeiten.
- Weitere Fachbereiche und Komfortfunktionen nur nach nachgewiesenem Nutzen aufnehmen.

## MVP-Abgrenzung

**Muss für den ersten nutzbaren Stand:** ein konkreter QGIS-Desktop-Ablauf mit geeigneten gemeinsamen Geodaten in PostGIS, wirksamen Rechten und nachgewiesener Wiederherstellbarkeit.

**Je nach Pilot:** Webviewer, mobile Erfassung, Suche, Datenexport, spezifische Datenmodelle.

**Nicht pauschal MVP:** vollständiger [Extract](ANHANG_A_GLOSSAR.md#extract)-Service, alle Fachbereiche, komplexe [CI/CD](ANHANG_A_GLOSSAR.md#ci-cd)- oder [HA](ANHANG_A_GLOSSAR.md#ha)-Plattform, umfassende Datenfreigabeworkflows.

## Prüfpunkte

- Funktionieren Kernabläufe mit echten Nutzern?
- Sind die Datenstände eindeutig und die Rechte wirksam?
- Ist der Betrieb mit verfügbaren IT-/GIS-Ressourcen realistisch?
- Werden zentrale Komponenten tatsächlich in beiden Piloten sinnvoll wiederverwendet?

Keine starren Termine oder Kosten ohne gesicherte Ressourcen- und Aufwandsschätzung.
