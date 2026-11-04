# Softwarekomponenten – Auswahl und Bewertung

**Status:** Bewertungsgerüst, 04.11.2026. **Keine neue Produktauswahl beschlossen.**

Hier werden **noch zu klärende Softwarekomponenten bzw. unmittelbar damit verbundene Lösungswege** systematisch verglichen. Jede Kategorie erhält eine eigene Datei mit denselben Abschnitten, Bewertungsmaßstäben, Quellenangaben und klarer Empfehlung bzw. offenem Prüfbedarf.

- [Bewertungsmethodik](BEWERTUNGSMETHODIK.md) – verbindliche Kriterien, Skala, Evidenz und Entscheidungsweg
- [Dokumentvorlage](VORLAGE.md) – einheitlicher Aufbau je Kategorie
- [Fiktiver Mustervergleich](BEISPIEL_DUMMY.md) – ausgefüllte Darstellung zum Prüfen des Formats, **keine reale Produktbewertung**

## Lizenz- und Kostenüberblick (GDI-Kern)

**Grundsatz:** Der vorgesehene GDI-Kern kann gewerblich mit freier Open-Source-Software **ohne zusätzliche Softwarelizenz- oder Nutzergebühren** aufgebaut werden. Die hier genannten Projekte/Editionen sind keine bereits abschließend geprüfte Softwarestückliste. **Open Source bedeutet nicht lizenzfrei:** Lizenz- und Hinweis-/Weitergabepflichten sind für die tatsächlich eingesetzten Versionen und Erweiterungen zu prüfen.

| Schicht / Werkzeug | Lizenz- und Kosteneinordnung | Nachweis / Vertiefung |
|---|---|---|
| QGIS Desktop | Freie Software, keine Nutzerlizenzgebühr | [QGIS-Lizenz](https://qgis.org/license/) |
| PostgreSQL / PostGIS | Freie Datenbank und räumliche Erweiterung, keine Softwarelizenzgebühr | [PostgreSQL-Lizenz](https://www.postgresql.org/about/licence/), [PostGIS-Lizenz](https://postgis.net/documentation/faq/gpl-license/) |
| QGIS Server (bevorzugt, offen) | Freier GIS-Server, keine Lizenzgebühr | [QGIS](https://qgis.org/download/), [SW-02](02_KARTENSERVER.md) |
| Lizmap / QWC2 (Kandidaten) | Freie Open-Source-Varianten, keine Lizenzgebühr für diese Editionen | [Lizmap](https://github.com/3liz/lizmap-web-client), [QWC2](https://github.com/qgis/qwc2), [SW-03](03_WEBVIEWER.md) |
| QField-App (vorhanden) | App kostenlos; gehostete QFieldCloud **separat** und ggf. kostenpflichtig | [QField-Lizenz](https://docs.qfield.org/get-started/license/), [SW-05](05_MOBILER_DATENAUSTAUSCH.md) |
| Debian (OS-Kandidat) und Git | Freie Standardsoftware ohne Lizenzgebühr; Betrieb/Hosting gesondert | [Debian](https://www.debian.org/intro/why_debian), [Git](https://git-scm.com/about/free-and-open-source), [SW-01](01_SERVERBETRIEBSSYSTEM.md) |
| Proxmox VE (bestehende/beschlossene Vorzugsinfrastruktur) | Ohne kostenpflichtige Lizenz betreibbar; **Enterprise-Repository/Herstellersupport optional per Subskription** | [Proxmox Einstieg](https://www.proxmox.com/de/produkte/proxmox-virtual-environment/erste-schritte), [Subskriptionen](https://www.proxmox.com/en/products/proxmox-virtual-environment/pricing), [IT-Briefing](../BRIEFING_IT.md#softwarelizenzen-und-optionaler-herstellersupport) |
| Docker Engine unter Linux (A24 offen) | Open-Source-Engine; **nicht mit Docker Desktop** und dessen ggf. kostenpflichtigen Unternehmenslizenzen verwechseln | [Engine](https://docs.docker.com/engine/), [Desktop-Lizenz](https://docs.docker.com/subscription-billing/desktop-license/) |

**Nicht von „keine zusätzlichen Softwarelizenzgebühren“ erfasst:** einmalige Einrichtung und Migration, interne Arbeitszeit, Schulung/Wissensaufbau, Administration, Infrastruktur-/Backup-Kapazitäten, externe Unterstützung, optionale Supportabos oder Cloudleistungen, proprietäre Zusatzprodukte sowie Nutzungsentgelte und Rechte an Geodaten. Für die wirtschaftliche Gesamtsicht und A39 ist [Umsetzung und Betrieb – Kostenrahmen](../06_UMSETZUNGS_UND_BETRIEBSMODELLE.md#kostenrahmen-und-lizenzabgrenzung) maßgeblich. Vor Pilotfreigabe tatsächliche Versionen, Abhängigkeiten, Lizenztexte, Open-Source-Pflichten und externe Datenrechte prüfen.

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
