# Softwarekomponenten – Auswahl und Bewertung

**Status:** Bewertungsgerüst, 04.11.2026. **Keine neue Produktauswahl beschlossen.**

Hier werden **noch zu klärende Softwarekomponenten bzw. unmittelbar damit verbundene Lösungswege** systematisch verglichen. Jede Kategorie erhält eine eigene Datei mit denselben Abschnitten, Bewertungsmaßstäben, Quellenangaben und klarer Empfehlung bzw. offenem Prüfbedarf.

- [Bewertungsmethodik](BEWERTUNGSMETHODIK.md) – verbindliche Kriterien, Skala, Evidenz und Entscheidungsweg
- [Dokumentvorlage](VORLAGE.md) – einheitlicher Aufbau je Kategorie
- [Fiktiver Mustervergleich](BEISPIEL_DUMMY.md) – ausgefüllte Darstellung zum Prüfen des Formats, **keine reale Produktbewertung**

## Kategorien und Reihenfolge

| ID | Kategorie | Bezug | Stand / Auslöser |
|---|---|---|---|
| SW-01 | [Serverbetriebssystem](01_SERVERBETRIEBSSYSTEM.md) | [A23](../04_ENTSCHEIDUNGEN.md#a23), [A24](../04_ENTSCHEIDUNGEN.md#a24) | IT-Auswahl offen; Proxmox ist bevorzugte vorhandene Infrastruktur, **nicht** das Gastbetriebssystem |
| SW-02 | [GIS-Kartenserver](02_KARTENSERVER.md) | [A10](../04_ENTSCHEIDUNGEN.md#a10) | QGIS Server bevorzugt, PoC und Alternativen offen |
| SW-03 | [Webviewer](03_WEBVIEWER.md) | [A11](../04_ENTSCHEIDUNGEN.md#a11), [A19](../04_ENTSCHEIDUNGEN.md#a19) | Open-Source-Lösung beschlossen; Auswahl offen, abhängig vom Pilot |
| SW-04 | [Metadatenkatalog](04_METADATENKATALOG.md) | [A15](../04_ENTSCHEIDUNGEN.md#a15) | **Ob eigene Katalogsoftware nötig ist, zuerst prüfen** |
| SW-05 | [Mobiler Datenaustausch](05_MOBILER_DATENAUSTAUSCH.md) | [A13](../04_ENTSCHEIDUNGEN.md#a13) | QField vorhanden; Cloud vs. lokaler Transfer offen |
| SW-06 | [Geodatenauszug](06_GEODATENAUSZUG.md) | [A12](../04_ENTSCHEIDUNGEN.md#a12) | Erst Bordmittel prüfen, separater Dienst nur bei Bedarf |

**Bewusst nicht als neue Produktauswahl eröffnet:** PostgreSQL/PostGIS ([A02](../04_ENTSCHEIDUNGEN.md#a02)), QGIS Desktop, Git und die vorhandene Proxmox-Virtualisierung sind in der Grundrichtung festgelegt bzw. vorhanden. Die [Deploymentvarianten A/B/C](../04_ENTSCHEIDUNGEN.md#a24) sind eine **Architekturentscheidung**, kein Wettbewerb zwischen einzelnen Softwareprodukten; die Bewertung erfolgt mit der IT im [IT-Briefing](../BRIEFING_IT.md#serverbetriebssystem-und-deployment-a23a24). Authentifizierung, Backup, Monitoring und ETL nutzen möglichst die bestehende IT-/GIS-Infrastruktur; dafür nur bei nachgewiesenem zusätzlichem Bedarf eine eigene Softwarekategorie anlegen.

## Verwendung und Pflege

1. Konkrete Pilotanforderungen und Muss-Kriterien mit GIS/Fachbereich/IT bestätigen.
2. Maximal zwei bis vier ernsthaft relevante Kandidaten einschließlich **„keine zusätzliche Software“**, wo sinnvoll, untersuchen.
3. Herstellerdokumentation, **Erstveröffentlichung, aktuelle stabile Version mit Datum und Entwicklungsaktivität der letzten 12 Monate**, Sicherheitsinformationen, externe Erfahrungsberichte und bei Bedarf PoC-Belege zuordnen. Bewertungsstichtag dokumentieren. **Nicht recherchierte Angaben bleiben `?`; nicht anwendbare Angaben werden als `n. a.` gekennzeichnet.**
4. Anhand der [Methodik](BEWERTUNGSMETHODIK.md) bewerten, sachliche Vor-/Nachteile formulieren und eine **vorläufige Empfehlung** mit Unsicherheiten kennzeichnen.
5. **Freigabe/Beschluss ausschließlich im [Entscheidungsregister](../04_ENTSCHEIDUNGEN.md)** festhalten. Die Einzeldateien sind Analyse, keine zweite Entscheidungsquelle.

Kein Produkt aufgrund von „mehr Funktionen“ empfehlen, wenn eine schlankere Lösung die bestätigten Anforderungen ausreichend erfüllt. Unterschiede beim Aufwand für Einführung, Updates, IT-Kompetenz, Lizenz-/Supportkosten und Datenhoheit ausdrücklich berücksichtigen.
