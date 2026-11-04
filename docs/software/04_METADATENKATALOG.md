# SW-04 – Metadatenkatalog

**Status:** Erstes Bewertungsgerüst · **Entscheidung:** offen · **Stand:** 04.11.2026  
**Entscheidungsbezug:** [A15](../04_ENTSCHEIDUNGEN.md#a15), [Prüfauftrag A15](../04_ENTSCHEIDUNGEN.md#katalogumfang-und-standards-a15) · [Methodik](BEWERTUNGSMETHODIK.md)

## 1. Zweck und Abgrenzung

Ein Metadatenkatalog soll Geodaten, Dienste und zugehörige Verantwortlichkeiten auffindbar machen. Für VIC-GDI ist zunächst eine schlanke, teils automatisch und teils redaktionell gepflegte Übersicht vorgesehen; **ob dafür ein eigenständiges Katalogprodukt erforderlich ist, steht ausdrücklich nicht fest**.

**Abgrenzung:** Der Metadatenkatalog ist weder eine zweite Geodatenhaltung noch zwingend ein öffentliches INSPIRE-/ISO-Metadatenportal. Die [integrierte Projektsuche](../04_ENTSCHEIDUNGEN.md#a20) ist nicht automatisch als separates Suchprodukt auszuschreiben.

## 2. Besondere Anforderungen

- **Muss:** Für die bestätigten Suchfälle mindestens Quellen, Datenstände, Zuständigkeiten, Nutzungsauflagen und Geodaten-/Dienstbezüge abbilden.
- **Muss:** Ergebnisse entsprechend den Berechtigungen sichtbar machen; keine ungewollte Freigabe vertraulicher Metadaten.
- **Soll:** Technische Felder aus vorhandenen Datenquellen übernehmen; redaktionelle Fachmetadaten einfach ergänzbar.
- **Offen:** Pilotumfang, Suchfelder, erforderliche Standards/Schnittstellen (z. B. OGC API – Records), Metadaten-Hoheit und Pflegeaufwand.

| Frage | Schlanke interne Metadatenlösung | pycsw | GeoNetwork |
|---|---|---|---|
| Bestätigte interne Such-/Pflegefälle abbildbar | ? | ? | ? |
| Keine Offenlegung geschützter Metadaten | ? | ? | ? |

**Hinweis:** `?` bedeutet **noch nicht nachgewiesen**, nicht `nicht erfüllt`.

## 3. Kandidaten (noch keine Auswahl)

| Kandidat | Charakter / Prüfansatz | Ausgangsquelle |
|---|---|---|
| **Schlanke interne Metadatenlösung** | Kein zusätzliches Katalogprodukt: vorhandene PostgreSQL-/GIS-Metadaten gezielt nutzen. | [Projekt-/Herstellerdokumentation](https://www.postgresql.org/docs/current/) |
| **pycsw** | Open-Source-Implementierung für Katalogschnittstellen; grundsätzlich API-/Backend-orientiert. | [Projekt-/Herstellerdokumentation](https://docs.pycsw.org/en/stable/) |
| **GeoNetwork** | Eigenständige Open-Source-Kataloganwendung mit Metadatenverwaltung. | [Projekt-/Herstellerdokumentation](https://docs.geonetwork-opensource.org/stable/) |

## 4. Vergleichsmatrix

Standardisierte Dimensionen und Gewichte nach [Methodik](BEWERTUNGSMETHODIK.md); `0–3` nur nach Quellenprüfung bzw. Test, sonst `?`.

**Produkt-/Release-Recherche noch ausstehend:** `?` = noch nicht geprüft, `n. a.` = kein eigenständig versioniertes Produkt bzw. gegenwärtig keine konkrete Software ausgewählt. Beim tatsächlichen Vergleich Erstveröffentlichung, Version samt Releasedatum und Aktivität der letzten 12 Monate mit offiziellem Release-/Changelog-Beleg und Bewertungsstichtag ergänzen. Diese drei Angaben werden nicht zusätzlich bepunktet.

| Dimension (Gewicht) | Schlanke interne Metadatenlösung | pycsw | GeoNetwork |
|---|---:|---:|---:|
| **Erstveröffentlichung / seit (Jahr)** | n. a. (kein separates Produkt) | ? | ? |
| **Aktuelle stabile Version (Releasedatum)** | n. a. (noch kein Produkt) | ? | ? |
| **Entwicklungsaktivität (12 Monate)** | n. a. (noch nicht implementiert) | ? | ? |
| Fachliche/funktionale Eignung (30 %) | ? | ? | ? |
| Integration/Interoperabilität (20 %) | ? | ? | ? |
| Sicherheit/Berechtigungen (15 %) | ? | ? | ? |
| Betrieb/Wartbarkeit (15 %) | ? | ? | ? |
| Reife/Zukunftsfähigkeit (10 %) | ? | ? | ? |
| Kosten/Lizenzen (10 %) | ? | ? | ? |
| **Gesamt (noch nicht berechenbar)** | — | — | — |
| **Evidenzstand** | E0 | E0 | E0 |

## 5. Vor- und Nachteile – vorläufige Prüfhypothesen

**Schlanke interne Metadatenlösung:** Wenige zusätzliche Dienste und passgenaue Felder könnten den Betrieb vereinfachen; Schnittstellen und Pflegeoberflächen dürften ggf. gezielte Implementierung erfordern. **Noch zu verifizieren:** Suchfunktionen, Rechte, Wartungsaufwand und Abgrenzung zur verbotenen unnötigen Eigenentwicklung.

**pycsw:** Standardisierte Katalogschnittstellen sind ein möglicher Vorteil; eine komplette komfortable Metadaten-Pflegeoberfläche gehört nicht automatisch zum Produkt. **Noch zu verifizieren:** Erforderliche GUI, unterstützte stabile Version, Rechteintegration, Lifecycle und Schnittstellen.

**GeoNetwork:** Umfassende Metadatenpflege könnte bei komplexeren Pflichten nützen; für einen rein internen schlanken Katalog könnte die zusätzliche Plattform zu aufwendig sein. **Noch zu verifizieren:** Integrationsbedarf, Pflege-/Betriebskosten, Rollen und notwendiger Standardumfang.

## 6. Bewertung und Empfehlung

**Aktueller Status: Noch keine belastbare Produktempfehlung.** Insbesondere ein eigener großer Katalogserver wäre nur zu rechtfertigen, wenn konkret bestätigte Such- und Pflegebedarfe mit vorhandenen Mitteln nicht angemessen lösbar sind.

**Nächster Schritt:** Zwei echte Such-/Pflegeabläufe und ihre Felder festlegen, danach zuerst die Lösung ohne zusätzliche Katalogsoftware erproben; Standardschnittstelle bzw. komplexes Produkt nur bei nachgewiesenem Bedarf vergleichen.

## 7. Quellen und Stand

- [PostgreSQL-Dokumentation](https://www.postgresql.org/docs/current/) – offizielle Dokumentation; Daten-/Such-/Rechtefunktionen als mögliche vorhandene Grundlage
- [pycsw – stabile Dokumentation](https://docs.pycsw.org/en/stable/) – offizielle Projektdoku für die stabile Produktlinie; angezeigt wird zur Prüfzeit **2.6.2**, Versions-/Releasedatum vor einer Entscheidung nochmals bestätigen
- [pycsw – Dokumentationsübersicht](https://pycsw.org/docs/) – offizielle Übersicht: *Current Release* und *Latest/master* ausdrücklich auseinanderhalten
- [pycsw – FAQ](https://pycsw.org/faq/) – Projekt-FAQ; insbesondere Grenzen der grafischen Oberfläche
- [GeoNetwork – Stable Docs](https://docs.geonetwork-opensource.org/stable/) – offizielle Dokumentation; Metadatenbearbeitung, Betrieb und APIs
- [OGC API – Records](https://docs.ogc.org/is/20-004r1/20-004r1.html) – Standard; nur bei konkret benötigter Interoperabilität

**Quellenstand:** Ausgangslinks am 04.11.2026 zusammengestellt; **keine vollständige Release-, Lizenz-, Sicherheits- oder Praxistestprüfung**. Unabhängige Bewertungen und Erfahrungsberichte sowie ggf. PoC-Ergebnisse werden beim echten Vergleich mit Version und Datum ergänzt.
