# Zielarchitektur VIC-GDI

**Status:** Interner Arbeitsentwurf · beschlossene Grundsätze und noch offene technische Festlegungen getrennt.

Die Architektur zeigt den bisherigen Beschlussstand. Zentrale [PostgreSQL](ANHANG_A_GLOSSAR.md#postgresql)-Projektablage und erweiterter interner Katalog mit hybrider Metadatenpflege sind [Prüfvarianten](04_ENTSCHEIDUNGEN.md#erneute-prüfung-a04-a15-und-a36) zu [A04](04_ENTSCHEIDUNGEN.md#a04), [A15](04_ENTSCHEIDUNGEN.md#a15) und [A36](04_ENTSCHEIDUNGEN.md#a36).

## Logische Architektur

- **Clients:** [QGIS](ANHANG_A_GLOSSAR.md#qgis) Desktop als Facharbeitsplatz; [Webviewer](ANHANG_A_GLOSSAR.md#webviewer) für vereinfachte und erweiterte Kartennutzung; [QField](ANHANG_A_GLOSSAR.md#qfield)/[HAPPY MINI Q](ANHANG_A_GLOSSAR.md#happy-mini-q) für geeignete mobile Online-/Offline-Szenarien.
- **Daten:** Gemeinsame PostgreSQL/[PostGIS](ANHANG_A_GLOSSAR.md#postgis)-Instanz mit fachbereichsbezogenen Schemas; projektbezogene Zuordnung über `project_id` nur, wo fachlich sinnvoll ([A02](04_ENTSCHEIDUNGEN.md#a02), [A03](04_ENTSCHEIDUNGEN.md#a03)).
- **Fachprojekte:** QGIS-Projekte bleiben fachbereichs- bzw. projektbezogen; zentral gepflegte Verbindungen, Vorlagen und [QML](ANHANG_A_GLOSSAR.md#qml)-Stile können wiederverwendet und überschrieben werden ([A04](04_ENTSCHEIDUNGEN.md#a04), [A17](04_ENTSCHEIDUNGEN.md#a17)).
- **Dienste:** [QGIS Server](ANHANG_A_GLOSSAR.md#qgis-server) bevorzugt, vorbehaltlich technischem [PoC](ANHANG_A_GLOSSAR.md#poc); Standard-Webviewer (z. B. [Lizmap](ANHANG_A_GLOSSAR.md#lizmap)/[QWC2](ANHANG_A_GLOSSAR.md#qwc2)) mit begrenzten Anpassungen; Webpublikation über getrennte Kartenprojekte ([A10](04_ENTSCHEIDUNGEN.md#a10), [A11](04_ENTSCHEIDUNGEN.md#a11), [A18](04_ENTSCHEIDUNGEN.md#a18)).
- **Zusatzfunktionen:** Schlanke integrierte Suche und [Geodatenauszug](ANHANG_A_GLOSSAR.md#extract) mit eigener Rechteprüfung ([A12](04_ENTSCHEIDUNGEN.md#a12), [A20](04_ENTSCHEIDUNGEN.md#a20)). Die logische Abgrenzung des Auszugs lässt die Bereitstellung offen. Für einen priorisierten Pilotbedarf zuerst vorhandene QGIS-, Viewer- und Dienstfunktionen prüfen.
- **Betrieb:** On-prem auf [Proxmox](ANHANG_A_GLOSSAR.md#proxmox) bevorzugt, hybride Varianten möglich; konkrete Container-/[VM](ANHANG_A_GLOSSAR.md#vm)-Verteilung mit IT entscheiden ([A23](04_ENTSCHEIDUNGEN.md#a23), [A24](04_ENTSCHEIDUNGEN.md#a24)).

**Lizenz-/Kostenprinzip:** Die hier vorgesehenen GDI-Kernkomponenten sind freie Open-Source-Software ohne zusätzliche Softwarelizenzgebühren. Proxmox VE ist ebenfalls ohne verpflichtende kostenpflichtige Lizenz nutzbar; eine Subskription für Enterprise-Repository/Support kann sich betrieblich empfehlen. Optional benötigte Drittanbieter-Dienste, Betriebsressourcen und die konkrete Softwarestückliste werden getrennt geprüft. Siehe [Softwarelizenzen und Kostenrahmen](ANHANG_C_SOFTWARE_LIZENZEN_KOSTEN.md). Dies legt keine der offenen Deploymentvarianten [A24](04_ENTSCHEIDUNGEN.md#a24) fest.

### Architekturübersicht (logisches Zielbild)

Das Diagramm zeigt die **wesentlichen Nutzungspfade und Datenhaltungen**, ohne einzelne technische Dienste oder Server aufzuschlüsseln. Der mobile Austausch ist noch zu validieren; gestrichelte Linien markieren mögliche, noch nicht festgelegte Zielanbindungen. Identität, Berechtigungen, Betrieb und Deployment gelten übergreifend und sind bewusst nicht als zusätzliche Pfeile dargestellt.

```mermaid
flowchart TB
  subgraph Nutzung["Nutzung"]
    Desktop["QGIS Desktop"]
    Web["Webviewer"]
    Mobile["QField / Happy MiniQ"]
  end
  subgraph Plattform["Gemeinsame GDI"]
    Map["GIS-Dienste / Kartenbereitstellung"]
    Data[("PostGIS: gemeinsame Vektordaten")]
    Files["Fileserver: QGIS-Projekte und Fachdateien"]
  end
  External["Externe Geodaten / Dienste"]
  MobileSync["Mobiler Datenaustausch: Weg offen"]
  Desktop --> Data
  Desktop --> Files
  Desktop --> External
  Web --> Map
  Map --> Data
  Map --> Files
  Map --> External
  Mobile <--> MobileSync
  MobileSync -.-> Data
  MobileSync -.-> Files
```

**Lesart:** QGIS Desktop arbeitet je nach Datenart mit PostGIS, Fileservern und externen Diensten. Der Webviewer nutzt [GIS](ANHANG_A_GLOSSAR.md#gis)-Dienste zur Kartenbereitstellung. Fachdateien verbleiben bei Bedarf auf dem Fileserver; geeignete gemeinsam bearbeitete Vektordaten liegen in PostGIS. Der mobile Rückweg und die Sicherheitsintegration sind noch zu konkretisieren.

## Datenorganisation

- Eine gemeinsame Projektidentität; schlanke Projektstammdaten und optionale räumliche Projektabgrenzung ([A06–A08](04_ENTSCHEIDUNGEN.md#a06)).
- Führende Stelle je gemeinsam genutztem Datenbestand; gemeinsame lesende Nutzung nach Freigabe, Schreibrechte nach Zuständigkeit ([A08](04_ENTSCHEIDUNGEN.md#a08), [A09](04_ENTSCHEIDUNGEN.md#a09)).
- Gemeinsam bearbeitete geeignete Vektordaten in PostGIS, QGIS-Projekte und geeignete Dateien auf Fileservern; keine pauschale Datenbankpflicht ([A36](04_ENTSCHEIDUNGEN.md#a36)).
- Amtliche externe Daten bevorzugt live nutzen; bei fachlicher Notwendigkeit unveränderliche, nachvollziehbare Datenstände anlegen ([A05](04_ENTSCHEIDUNGEN.md#a05)).
- Externe Rasterdienste bevorzugen; lokale [GeoTIFF](ANHANG_A_GLOSSAR.md#geotiff)/[COG](ANHANG_A_GLOSSAR.md#cog) für Analyse und Reproduzierbarkeit, kein genereller PostGIS-Raster-Zwang ([A22](04_ENTSCHEIDUNGEN.md#a22)).
- ETRS89/[UTM](ANHANG_A_GLOSSAR.md#utm) EPSG:25832 oder 25833 nach räumlichem Bezug bevorzugen; historische/lokale Projekt-[CRS](ANHANG_A_GLOSSAR.md#crs) und Höhenreferenzen ausdrücklich berücksichtigen ([A21](04_ENTSCHEIDUNGEN.md#a21)).

## GIS-Funktionen

- **Suche:** Projekte, Orte/Adressen und ausgewählte GIS-Objekte; Ergebnisse nur entsprechend Berechtigung ([A20](04_ENTSCHEIDUNGEN.md#a20)).
- **Auszug:** Autorisierte Layer, Geometrie/Fläche/[BBox](ANHANG_A_GLOSSAR.md#bbox), Ziel-CRS, [GPKG](ANHANG_A_GLOSSAR.md#geopackage)/[Shapefile](ANHANG_A_GLOSSAR.md#shapefile)/[GeoJSON](ANHANG_A_GLOSSAR.md#geojson)/[CSV](ANHANG_A_GLOSSAR.md#csv). Objektselektion und echtes geometrisches Clipping unterscheiden; technischer PoC erforderlich ([A12](04_ENTSCHEIDUNGEN.md#a12)).
- **Mobil:** Vorhandene Synchronisationsmechanismen verwenden; Konfliktbehandlung und Rückübertragung pilotieren, keine eigene Offline-Engine ([A13](04_ENTSCHEIDUNGEN.md#a13)).
- **[ETL](ANHANG_A_GLOSSAR.md#etl):** Manuelle Verfahren und Skripte zuerst; kontrollierte Staging-/Importprüfungen, später selektiv automatisieren ([A14](04_ENTSCHEIDUNGEN.md#a14)).
- **Metadaten:** Schlanker Katalog für Quelle, Datensatz und Dienst; je Layer u. a. Herkunft, Datenstand, Lizenz, Importzeit, CRS ([A15](04_ENTSCHEIDUNGEN.md#a15)).
- **Qualität:** Amtliche Daten nur auf technische Import-/Transformationsfehler prüfen; eigene gemeinsame Daten fachlich im normalen Arbeitsprozess plausibilisieren, ohne formalen Freigabeapparat ([A16](04_ENTSCHEIDUNGEN.md#a16)).

## Sicherheits- und Betriebsprinzipien

- Rechte nicht allein über ausgeblendete UI-Elemente, sondern auf den jeweiligen Server-/Datenzugriffspfaden durchsetzen ([A09](04_ENTSCHEIDUNGEN.md#a09), [A26](04_ENTSCHEIDUNGEN.md#a26)).
- Vorhandene Unternehmensidentitäten bevorzugt nutzen. IT klärt, welche Rolle [AD DS](ANHANG_A_GLOSSAR.md#ad) und [Microsoft Entra ID](ANHANG_A_GLOSSAR.md#entra-id) für Browseranmeldung, direkten Datenbankzugriff und externe Konten übernehmen können ([A25](04_ENTSCHEIDUNGEN.md#a25)).
- Getrennte TEST-/PROD-Umgebung, versionierte Konfiguration und Datenbankmigrationen, kontrollierte Bereitstellung ([A27](04_ENTSCHEIDUNGEN.md#a27), [A30](04_ENTSCHEIDUNGEN.md#a30)).
- Bestehende IT-Backups und Monitoring nutzen, um [GDI](ANHANG_A_GLOSSAR.md#gdi)-spezifische Prüfungen und Restore-Tests ergänzen ([A28](04_ENTSCHEIDUNGEN.md#a28), [A29](04_ENTSCHEIDUNGEN.md#a29)).

## Bewusst nicht festgelegt

Deploymentmodell [A24](04_ENTSCHEIDUNGEN.md#a24), Details des Identitäts- und Berechtigungsmodells, Datenlebenszyklus [A37](04_ENTSCHEIDUNGEN.md#a37) und konkrete Datenbankvalidierung [A38](04_ENTSCHEIDUNGEN.md#a38). Diese Themen sind in [07_OFFENE_PUNKTE.md](07_OFFENE_PUNKTE.md) dokumentiert. Nicht jede hier genannte bevorzugte Technologie ist bereits technisch freigegeben.
