# Roadmap und Einführung

**Status:** Interner Arbeitsentwurf · keine Termin-, Budget- oder Personalzusage.

VIC-GDI ist eine fachlich vom GIS-Team und beteiligten Fachkollegen vorangetriebene Infrastrukturinitiative. Die [Pilotkonkretisierung](05_PILOTKONKRETISIERUNG.md) dokumentiert die fachliche Ausgangslage und mögliche erste Einsatzabläufe. **Die Piloten sind gestaffelte Schritte zur Einführung der GDI**; auszuwählen und abzunehmen sind die konkreten Abläufe und technischen Lösungen, nicht der grundsätzliche Nutzen einer GDI.

## Vorgehensprinzip

Gemeinsame, schlanke [GDI](ANHANG_A_GLOSSAR.md#gdi)-Basis und zwei früh beteiligte Pilotbereiche ([A34](04_ENTSCHEIDUNGEN.md#a34)). Der [MVP](ANHANG_A_GLOSSAR.md#mvp) ist priorisiert und anpassbar; gemeinsamer GDI-MVP und fachliche Pilot-MVPs werden getrennt geplant ([A35](04_ENTSCHEIDUNGEN.md#a35)). Phasen dürfen sich überlappen.

### Vorbereitung der gestaffelten GDI-Einführung

```mermaid
flowchart LR
  Prepare["Ressourcen und Ist-Abläufe konkretisieren"]
  Model["A39: Umsetzung, Wissen und Betrieb bewerten"]
  Select["Erste Einführungsabläufe und Umfang festlegen"]
  Release["Gezielten Techniktest freigeben"]
  Test["Technische Detailfrage absichern"]
  Decide{"Produktiven Pilot freigeben?"}
  Use["Ersten GDI-Ausbauschritt umsetzen"]
  Prepare --> Model --> Select
  Select -->|Technische Detailfrage offen| Release
  Release --> Test --> Decide
  Select -->|Technik ausreichend geklärt| Decide
  Decide -->|Ja, inkl. tragfähigem Betrieb| Use
  Decide -->|Rahmen anpassen| Model
```

Aktuell laufen die Planung und Abstimmung der **fachlich gewünschten GDI-Einführung**. Die IT klärt den Betriebsrahmen, die Geschäftsführung entscheidet über die notwendigen Vorbereitungsressourcen. **Gezielte technische Tests** erfolgen bei Bedarf nach gesonderter Freigabe. Über Umfang, Budget und Start der Piloten entscheidet die Geschäftsführung anhand der Ergebnisse und des mit IT geklärten Betriebsrahmens. Siehe [Mindestabnahme für den Betrieb](BRIEFING_IT.md#mindestabnahme-vor-produktivem-pilot) und [Folgeentscheidung der Geschäftsführung](BRIEFING_GESCHAEFTSFUEHRUNG.md#folgeentscheidung).

## Entscheidungstore und Abhängigkeiten

| Entscheidungstor | Erforderliche Grundlage | Ergebnis |
|---|---|---|
| **Vorbereitung ermöglichen** | Fachlich begründete Zielsetzung, Pilotvorschläge, Ansprechpersonen, grober GIS-/IT-Planungsauftrag | GF legt priorisierte Vorbereitungsressourcen fest; **keine Umsetzungsfreigabe** |
| **A39-Richtung bewerten** | Verfügbare Kompetenzen/Kapazitäten, realistische interne/externe Varianten, Qualifizierung, Kostenfelder, dauerhafte Verantwortung | GF/IT erarbeiten bzw. treffen in ihren Zuständigkeiten die tragfähige Organisationsrichtung; fehlende Voraussetzungen ausdrücklich dokumentieren |
| **Gezielte Erprobung freigeben (falls nötig)** | Konkrete offene Machbarkeitsfrage, begrenzter Testumfang und Zuständigkeit | Separate Freigabe für einen PoC, **noch kein produktiver Pilot** |
| **Produktiven Pilot freigeben** | Abgestimmter Pilot-/MVP-Umfang und Abnahmekriterien, Sicherheit/Rechte, Backup/Restore, Betriebsverantwortung und Ressourcen | GF entscheidet über Umfang/Budget, IT über tragfähigen Betrieb; fachliche Abnahme durch Pilotbereiche |

**A39 ist vorrangig, aber kein Totalstopp:** Für eine vernünftige A39-Bewertung dürfen fachliche Pilotfälle, ein logisches Zielbild und grobe technische Aufwandstreiber bereits geklärt werden. Detailauswahl und Optimierung ohne unmittelbaren Einfluss auf A39 oder einen konkret freigegebenen Pilot werden zurückgestellt. [Priorisierte offene Punkte](08_OFFENE_PUNKTE.md#arbeitspriorität-nach-entscheidungshorizont).

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
- **Verkehrsanlagenplanung:** gemeinsame [Geodaten](ANHANG_A_GLOSSAR.md#geodaten), Projektbezug und QGIS-Workflows.
- Fachliche Abnahme an realen Daten; keine Pflicht zu gleichem Funktionsumfang.

### 3 – Stabilisierung und kontrollierte Migration
- OneDrive-/SharePoint-basierte führende GIS-Arbeitsbestände der BB nach [A36](04_ENTSCHEIDUNGEN.md#a36) kontrolliert ablösen.
- Datenquellen, Mehrbenutzerbearbeitung, Datenhoheit und Berechtigungen testen.
- Betriebs-, Schulungs- und Supportaufwand aus der Praxis erfassen.

### 4 – Review und Ausbau
- Die im ersten Ausbauschritt erreichten Verbesserungen dokumentieren; Bedienbarkeit, Datenqualität, Wartbarkeit, Ressourcen und Akzeptanz bewerten.
- Architektur und Arbeitsabläufe anhand der Betriebserfahrungen gezielt verbessern; offene Entscheidungen bearbeiten.
- Weitere Fachbereiche und Komfortfunktionen nach fachlichen Prioritäten, vorhandenen Kapazitäten und Betriebserfahrungen aufnehmen.

## MVP-Abgrenzung

**Muss für den ersten nutzbaren Stand:** ein konkreter QGIS-Desktop-Ablauf mit geeigneten gemeinsamen Geodaten in PostGIS, wirksamen Rechten und nachgewiesener Wiederherstellbarkeit.

**Je nach Pilot:** Webviewer, mobile Erfassung, Suche, **Geodatenauszug nach [A12](04_ENTSCHEIDUNGEN.md#a12) (beide räumlichen Verfahren vorgesehen; GPKG/GeoJSON/DXF/CSV, Shapefile optional; Rechte vor Freischaltung prüfen)**, spezifische Datenmodelle.

**Nicht pauschal MVP:** eigenständiger [Extract](ANHANG_A_GLOSSAR.md#extract)-Service (A12 verlangt nur die Funktion; vorhandene Exportmöglichkeiten zuerst nutzen), alle Fachbereiche, komplexe [CI/CD](ANHANG_A_GLOSSAR.md#ci-cd)- oder [HA](ANHANG_A_GLOSSAR.md#ha)-Plattform, umfassende Datenfreigabeworkflows.

## Prüfpunkte

- Funktionieren Kernabläufe mit echten Nutzern?
- Sind die Datenstände eindeutig und die Rechte wirksam?
- Ist der Betrieb mit verfügbaren IT-/GIS-Ressourcen realistisch?
- Werden zentrale Komponenten tatsächlich in beiden Piloten sinnvoll wiederverwendet?

Keine starren Termine oder Kosten ohne gesicherte Ressourcen- und Aufwandsschätzung.
