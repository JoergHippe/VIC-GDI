# Roadmap und Einführung

**Status:** Interner Arbeitsentwurf · keine Termin-, Budget- oder Personalzusage.

## Vorgehensprinzip

Gemeinsame, schlanke GDI-Basis und zwei früh beteiligte Pilotbereiche (A34). Der MVP ist priorisiert und anpassbar; gemeinsamer GDI-MVP und fachliche Pilot-MVPs werden getrennt geplant (A35). Phasen dürfen sich überlappen.

## Etappen

### 0 – Vorbereitung und Bestandsaufnahme
- IT, GIS-Team und Pilotbereiche abstimmen; Zuständigkeiten skizzieren.
- Bestehende QGIS-Projekte, Datenquellen, Speicherorte und kritische Abläufe erfassen.
- Problematische synchronisierte SharePoint-/OneDrive-GIS-Arbeitsdatenhaltung in der Baubetreuung identifizieren.
- Konkrete Pilot-Use-Cases und Minimalerfolgskriterien festlegen.
- Wissens- und Schulungsbedarf samt Kapazitäten einplanen (A33).

### 1 – Gemeinsame technische Basis
- PostGIS und QGIS-Desktop-Anbindung; geeignete gemeinsame Datenmodelle.
- TEST/PROD, Grundrechte, Sicherung und Basisüberwachung mit IT abstimmen.
- Git-basierte Ressourcen und kontrollierte Änderungen etablieren.
- QGIS-Server-/Webviewer-PoC und einfache Kartenbereitstellung.

### 2 – Erste nutzbare Pilotfunktionen
- **BB:** ausgewählte räumliche Arbeitsabläufe und, wo erforderlich, mobile Nutzung.
- **Verkehrsanlagenplanung:** gemeinsame Geodaten, Projektbezug und QGIS-Workflows.
- Fachliche Abnahme an realen Daten; keine Pflicht zu gleichem Funktionsumfang.

### 3 – Stabilisierung und kontrollierte Migration
- OneDrive-/SharePoint-basierte führende GIS-Arbeitsbestände der BB nach A36 kontrolliert ablösen.
- Datenquellen, Mehrbenutzerbearbeitung, Datenhoheit und Berechtigungen testen.
- Betriebs-, Schulungs- und Supportaufwand aus der Praxis erfassen.

### 4 – Review und Ausbau
- Nutzen, Bedienbarkeit, Datenqualität, Wartbarkeit, Ressourcen und Akzeptanz bewerten.
- Architektur bei Bedarf korrigieren, offene Entscheidungen gezielt bearbeiten.
- Weitere Fachbereiche und Komfortfunktionen nur nach nachgewiesenem Nutzen aufnehmen.

## MVP-Abgrenzung

**Muss für den ersten nutzbaren Stand:** sicherer Datenzugriff, geeignete zentrale Datenhaltung, funktionierende QGIS-Arbeitsabläufe, notwendige Sicherung/Wiederherstellung und ein konkret nutzbarer Pilotfall.

**Je nach Pilot:** Webviewer, mobile Erfassung, Suche, Datenexport, spezifische Datenmodelle.

**Nicht pauschal MVP:** vollständiger Extract-Service, alle Fachbereiche, komplexe CI/CD- oder HA-Plattform, umfassende Datenfreigabeworkflows.

## Prüfpunkte

- Funktionieren Kernabläufe mit echten Nutzern?
- Sind die Datenstände eindeutig und die Rechte wirksam?
- Ist der Betrieb mit verfügbaren IT-/GIS-Ressourcen realistisch?
- Werden zentrale Komponenten tatsächlich in beiden Piloten sinnvoll wiederverwendet?

Keine starren Termine oder Kosten ohne gesicherte Ressourcen- und Aufwandsschätzung.
