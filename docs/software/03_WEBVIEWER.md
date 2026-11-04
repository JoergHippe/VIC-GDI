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
| **QWC2 / QWC** | Modularer responsiver QGIS-Webclient; optional mit weiteren QWC-Services. | [Projekt-/Herstellerdokumentation](https://docs.qwc.app/) |

## 4. Vergleichsmatrix

Standardisierte Dimensionen und Gewichte nach [Methodik](BEWERTUNGSMETHODIK.md); `0–3` nur nach Quellenprüfung bzw. Test, sonst `?`.

| Dimension (Gewicht) | Lizmap | QWC2 / QWC |
|---|---:|---:|
| Fachliche/funktionale Eignung (30 %) | ? | ? |
| Integration/Interoperabilität (20 %) | ? | ? |
| Sicherheit/Berechtigungen (15 %) | ? | ? |
| Betrieb/Wartbarkeit (15 %) | ? | ? |
| Reife/Zukunftsfähigkeit (10 %) | ? | ? |
| Kosten/Lizenzen (10 %) | ? | ? |
| **Gesamt (noch nicht berechenbar)** | — | — |
| **Evidenzstand** | E0 | E0 |

## 5. Vor- und Nachteile – vorläufige Prüfhypothesen

**Lizmap:** Die QGIS-nahe Konfiguration kann den Publikationsablauf vereinfachen; Kompatibilität, Anpassbarkeit und benötigte Zusatzfunktionen sind zu prüfen. **Noch zu verifizieren:** Leichtgewichtige Ansicht, Gruppenrechte, Suche, Performance und Wartung.

**QWC2 / QWC:** Modularität kann eine passgenaue Oberfläche ermöglichen; Build-/Konfigurations- und ggf. zusätzliche Backenddienste können den Betrieb komplexer machen. **Noch zu verifizieren:** Erforderliche Backenddienste, Rollen, Konfigurationsaufwand, einfache Tablet-Ansicht.

## 6. Bewertung und Empfehlung

**Aktueller Status: Noch keine belastbare Produktempfehlung.** Für einen Pilot ohne Webkartenbedarf ist der Rollout verschiebbar; für die Zielarchitektur bleibt eine Standard-Open-Source-Lösung vorgesehen.

**Nächster Schritt:** Je eine einfache Pilotkarte mit typischen Rollen und Tablet-Bedienung durchspielen. Ohne bewiesenen Bedarf keine zusätzlichen Backend-Module oder eigene Frontend-Entwicklung einführen.

## 7. Quellen und Stand

- [Lizmap – offizielle Dokumentation](https://docs.lizmap.com/current/en/) – Projektdoku; Publikation, Authentifizierung, Installationsanforderungen
- [QWC / QWC Services](https://docs.qwc.app/) – Projektdoku; Standalone versus Backend-Dienste
- [QWC2 – QGIS-DE](https://qgis.de/doku.php/site/qgisserver/qwc2) – Community-Material; Anwendungsaufbau; Versionsaktualität gesondert prüfen

**Quellenstand:** Ausgangslinks am 04.11.2026 zusammengestellt; **keine vollständige Release-, Lizenz-, Sicherheits- oder Praxistestprüfung**. Unabhängige Bewertungen/Erfahrungsberichte und gegebenenfalls PoC-Ergebnisse werden beim echten Vergleich mit Version und Datum ergänzt.
