# SW-02 – GIS-Kartenserver

**Status:** Erstes Bewertungsgerüst · **Entscheidung:** offen · **Stand:** 04.11.2026  
**Entscheidungsbezug:** [A10](../04_ENTSCHEIDUNGEN.md#a10), [A18](../04_ENTSCHEIDUNGEN.md#a18) · [Methodik](BEWERTUNGSMETHODIK.md)

## 1. Zweck und Abgrenzung

Ein GIS-Kartenserver stellt Karten und gegebenenfalls Geodaten über standardisierte Dienste für interne Browser- und Desktop-Nutzung bereit. Im VIC-Kontext sollen freigegebene QGIS-Webprojekte und PostGIS-Daten nachvollziehbar und rechtssicher veröffentlicht werden. **QGIS Server ist die bereits bevorzugte, aber noch nicht validierte Richtung.**

**Abgrenzung:** Der Kartenserver ist **nicht** der Webviewer, keine vollständige Datenkataloglösung und kein Ersatz für serverseitige Datenbank-/Dienstberechtigungen.

## 2. Besondere Anforderungen

- **Muss:** Für den Pilot benötigte OGC-Dienste und zuverlässige Veröffentlichung der freigegebenen Karten.
- **Muss:** Rechte für veröffentlichte Inhalte auch bei direktem Aufruf eines Endpunkts wirksam durchsetzen.
- **Soll:** QGIS-Projektstile und Drucklayouts soweit erforderlich ohne doppelte Kartenpflege nutzen.
- **Offen:** Benötigte Dienste (z. B. WMS/WFS), Last, Authentifizierung, Betrieb und Viewer-Kopplung.

| Muss-Prüfung | QGIS Server | GeoServer | MapServer |
|---|---|---|---|
| Pilotkarte aus vorgesehenen Daten bereitstellbar | ? | ? | ? |
| Berechtigungen auf Dienstebene durchsetzbar | ? | ? | ? |

**Hinweis:** Die Prüfung ist noch nicht erfolgt; `?` bedeutet **nicht nachgewiesen**, nicht `nicht erfüllt`.

## 3. Kandidaten (noch keine Auswahl)

| Kandidat | Charakter / Prüfansatz | Ausgangsquelle |
|---|---|---|
| **QGIS Server** | QGIS-projektbasierte Kartenbereitstellung; bisher bevorzugt. | [Projekt-/Herstellerdokumentation](https://www.qgis.org/project/overview/) |
| **GeoServer** | Eigenständiger Open-Source-Geodatenserver und alternative OGC-Dienstplattform. | [Projekt-/Herstellerdokumentation](https://docs.geoserver.org/main/en/user/introduction/overview/) |
| **MapServer** | Schlanker Open-Source-Kartenserver als Referenzalternative. | [Projekt-/Herstellerdokumentation](https://mapserver.github.io/) |

## 4. Vergleichsmatrix

**Bewertung noch nicht begonnen:** Alle bisherigen Punkte- und Produktstandfelder waren `?` bzw. `n. a.`; eine ausgefüllte Matrix würde hier fälschlich eine belastbare Vergleichsstufe suggerieren. QGIS Server bleibt bevorzugter, aber noch nicht technisch freigegebener Kandidat; alternative Server werden nur bei relevantem Funktionsbedarf bewertet.

Sobald ein bestätigter Pilotbedarf eine echte Auswahl erforderlich macht, die [standardisierte Vergleichsmatrix](VORLAGE.md#4-vergleichsmatrix) nach [Methodik](BEWERTUNGSMETHODIK.md) mit aktuellem Produkt-/Versionsstand, nachgewiesenen Muss-Kriterien, Quellen und Bewertungsstichtag erstellen. **Keine Rangfolge oder Gesamtpunktzahl ohne Belege.**

## 5. Vor- und Nachteile – vorläufige Prüfhypothesen

**QGIS Server:** Direkter Bezug zu QGIS-Projekten kann getrennte Stylepflege reduzieren; die Eignung für Rechte, Last und konkreten Betrieb muss bewiesen werden. **Noch zu verifizieren:** Rechte/SSO, Webkartenstile, Dienste, Performance und Sicherheit.

**GeoServer:** Breites Dienstangebot kann bei heterogenen Anforderungen helfen; eine zusätzliche parallele Konfiguration und Infrastruktur könnte mehr Aufwand verursachen. **Noch zu verifizieren:** Veröffentlichung bestehender QGIS-Karten, Administration, Security-Updates, funktionaler Mehrwert.

**MapServer:** Eine fokussierte Kartenbereitstellung kann für einfache Dienste geeignet sein; Projekt-/Style-Übernahme aus QGIS und Rechteintegration könnten Mehraufwand bedeuten. **Noch zu verifizieren:** Abdeckung des konkret geforderten Funktionsumfangs und Rechtepfad.

**Lizenzabgrenzung:** Der bevorzugte [QGIS Server](https://qgis.org/download/) ist frei verfügbar und erfordert für die Open-Source-Software keine zusätzliche Nutzer- oder Serverlizenzgebühr. Betrieb, Konfiguration, Absicherung sowie eventuelle Zusatzdienste sind nicht kostenfrei. Bei alternativen Produkten sind Lizenz und benötigte Edition einzeln zu belegen.

## 6. Bewertung und Empfehlung

**Aktueller Status: Noch keine belastbare Produktempfehlung.** Die bisherige Präferenz für QGIS Server wird **nicht** zu einem formalen Beschluss hochgestuft; andere Produkte sind nur Vergleichskandidaten.

**Nächster Schritt:** Mit einer realen QGIS-Pilotkarte direkte Veröffentlichung, WMS-/ggf. WFS-Verhalten, Rechte und Betrieb testen; nur bei fachlich/technischem Mehrwert Alternativen vertiefen.

## 7. Quellen und Stand

- [QGIS-Überblick mit QGIS Server](https://www.qgis.org/project/overview/) – offizielle Produktseite; QGIS-Projekte/OGC-Dienste
- [GeoServer – Einführung](https://docs.geoserver.org/main/en/user/introduction/overview/) – offizielle Dokumentation; Diensttypen und Grundlagen
- [MapServer – Dokumentation](https://mapserver.github.io/) – offizielle Projektdokumentation; Betrieb und Dienste
- [GeoServer bei OSGeo](https://www.osgeo.org/projects/geoserver/) – externes Projektprofil; Zusatzkontext, kein Ersatz für Praxistests

**Quellenstand:** Ausgangslinks am 04.11.2026 zusammengestellt; **keine vollständige Release-, Lizenz-, Sicherheits- oder Praxistestprüfung**. Unabhängige Bewertungen/Erfahrungsberichte und gegebenenfalls PoC-Ergebnisse werden beim echten Vergleich mit Version und Datum ergänzt.
