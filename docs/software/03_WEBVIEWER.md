# SW-03 – Webviewer

**Status:** Erstes Bewertungsgerüst · **Entscheidung:** offen · **Stand:** 04.11.2026  
**Entscheidungsbezug:** [A11](../04_ENTSCHEIDUNGEN.md#a11), [A19](../04_ENTSCHEIDUNGEN.md#a19) · [Methodik](BEWERTUNGSMETHODIK.md)

## 1. Zweck und Abgrenzung

Ein Webviewer ermöglicht die einfache Anzeige freigegebener Karten und Abfragen im Browser, insbesondere für gelegentliche GIS-Anwender und bei Bedarf auf Tablets. Die Architektur setzt auf eine **etablierte Open-Source-Anwendung statt eines selbst entwickelten GIS-Portals**.

**Abgrenzung:** Der Viewer ersetzt weder einen GIS-Kartenserver noch die notwendigen serverseitigen Berechtigungen. Die tatsächlich erforderlichen Viewer-Funktionen werden aus den Pilotabläufen abgeleitet.

## 2. Besondere Anforderungen

- **Muss:** Einfach bedienbare Kartenansicht mit bedarfsgerechten, responsiven Oberflächen; erforderliche Nutzerrechte nicht nur in der UI.
- **Muss:** Mit den vorgesehenen QGIS-Server-/OGC-Diensten und bestehenden IT-Zugängen zusammenarbeiten.
- **Soll:** Suche, Layer-/Objektinfos, optional Druck und zusätzliche Expertenwerkzeuge ohne überladene Startansicht.
- **Offen:** Tablet-Priorität, konkrete Suchfälle, Benutzerverwaltung, benötigte Zusatzdienste.

| Muss-Prüfung | Lizmap | QWC2 / QWC |
|---|---|---|
| Abgesicherte Darstellung der Pilotkarten | ? | ? |
| Einfacher und auf Tablets nutzbarer Basismodus | ? | ? |

**Hinweis:** Die Prüfung ist noch nicht erfolgt; `?` bedeutet **nicht nachgewiesen**, nicht `nicht erfüllt`.

## 3. Kandidaten (noch keine Auswahl)

| Kandidat | Charakter / Prüfansatz | Ausgangsquelle |
|---|---|---|
| **Lizmap** | Webkartenbereitstellung auf Basis von QGIS Server. | [Projekt-/Herstellerdokumentation](https://docs.lizmap.com/current/en/) |
| **QWC2 / QWC** | Responsive QGIS-Webclients; Frontend und optionale QWC-Backenddienste getrennt betrachten. | [QWC2-Frontend](https://github.com/qgis/qwc2), [aktuelle QWC-Dokumentation](https://docs.qwc.app/) |

**Versions- und Architekturabgrenzung:** [QWC2](https://github.com/qgis/qwc2) bezeichnet das Frontend-Projekt; die [QWC-Dokumentation](https://docs.qwc.app/) beschreibt auch die neuere QWC-Veröffentlichung und den optionalen Einsatz von **qwc-services**. Ein eigenständig bereitgestellter Viewer und eine Kombination aus Viewer **plus** Backenddiensten verursachen unterschiedliche Betriebs-, Rechte- und Integrationsaufwände. Vor einer echten Bewertung die konkret geprüfte **Release-Linie** samt benötigter Services festlegen und **nicht** die Angaben verschiedener Generationen vermischen.

## 4. Vergleichsmatrix

**Bewertung noch nicht begonnen:** Alle bisherigen Punkte- und Produktstandfelder waren `?` bzw. `n. a.`; eine ausgefüllte Matrix würde hier fälschlich eine belastbare Vergleichsstufe suggerieren. Lizmap und QWC2 bleiben Kandidaten; ein Produktvergleich setzt bestätigte Pilotanforderungen voraus.

Sobald ein bestätigter Pilotbedarf eine echte Auswahl erforderlich macht, die [standardisierte Vergleichsmatrix](VORLAGE.md#4-vergleichsmatrix) nach [Methodik](BEWERTUNGSMETHODIK.md) mit aktuellem Produkt-/Versionsstand, nachgewiesenen Muss-Kriterien, Quellen und Bewertungsstichtag erstellen. **Keine Rangfolge oder Gesamtpunktzahl ohne Belege.**

## 5. Vor- und Nachteile – vorläufige Prüfhypothesen

**Lizmap:** Die QGIS-nahe Konfiguration kann den Publikationsablauf vereinfachen; Kompatibilität, Anpassbarkeit und benötigte Zusatzfunktionen sind zu prüfen. **Noch zu verifizieren:** Leichtgewichtige Ansicht, Gruppenrechte, Suche, Performance und Wartung.

**QWC2 / QWC:** Modularität kann eine passgenaue Oberfläche ermöglichen; Build-/Konfigurations- und ggf. zusätzliche Backenddienste können den Betrieb komplexer machen. **Noch zu verifizieren:** Erforderliche Backenddienste, Rollen, Konfigurationsaufwand, einfache Tablet-Ansicht.

**Lizenzabgrenzung:** [Lizmap](https://github.com/3liz/lizmap-web-client) und [QWC2](https://github.com/qgis/qwc2) sind in den betrachteten Open-Source-Varianten ohne zusätzliche Softwarelizenzgebühr nutzbar. Gehostete Angebote, individuelle Erweiterungen, Zusatzdienste und laufender Betrieb sind hiervon nicht automatisch erfasst. Die konkret verwendete QWC-Release-Linie und Komponentenliste vor der Lizenzprüfung eindeutig bestimmen.

## 6. Bewertung und Empfehlung

**Aktueller Status: Noch keine belastbare Produktempfehlung.** Für einen Pilot ohne Webkartenbedarf ist der Rollout verschiebbar; für die Zielarchitektur bleibt eine Standard-Open-Source-Lösung vorgesehen.

**Nächster Schritt:** Je eine einfache Pilotkarte mit typischen Rollen und Tablet-Bedienung durchspielen. Ohne bewiesenen Bedarf keine zusätzlichen Backend-Module oder eigene Frontend-Entwicklung einführen.

## 7. Quellen und Stand

- [Lizmap – offizielle Dokumentation](https://docs.lizmap.com/current/en/) – Projektdoku; Publikation, Authentifizierung, Installationsanforderungen
- [QWC2 – Frontend-/Quellcode](https://github.com/qgis/qwc2) – Upstream-Repository; Versions- und Entwicklungsstand getrennt prüfen
- [QWC – aktuelle Dokumentation](https://docs.qwc.app/) – Projektdoku; Standalone versus optionale Backenddienste/qwc-services
- [QWC2 – QGIS-DE](https://qgis.de/doku.php/site/qgisserver/qwc2) – älterer Community-Leitfaden; nur als historische Einordnung verwenden, nicht als Nachweis aktueller Releases

**Quellenstand:** Ausgangslinks am 04.11.2026 zusammengestellt; **keine vollständige Release-, Lizenz-, Sicherheits- oder Praxistestprüfung**. Unabhängige Bewertungen/Erfahrungsberichte und gegebenenfalls PoC-Ergebnisse werden beim echten Vergleich mit Version und Datum ergänzt.
