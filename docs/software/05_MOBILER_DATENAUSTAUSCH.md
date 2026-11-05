# SW-05 – Mobiler Datenaustausch

**Status:** Erstes Bewertungsgerüst · **Entscheidung:** offen · **Stand:** 04.11.2026  
**Entscheidungsbezug:** [A13](../04_ENTSCHEIDUNGEN.md#a13), [Pilot Baubetreuung](../05_PILOTKONKRETISIERUNG.md#mobile-erfassung-und-datenaustausch) · [Methodik](BEWERTUNGSMETHODIK.md)

## 1. Zweck und Abgrenzung

Die Baubetreuung nutzt QField mit GNSS-Empfänger auf Mobilgeräten. Offen ist der zuverlässige **bidirektionale Austausch** zwischen mobilen Erfassungsständen und fachlich geprüften zentralen Daten. Eine eigene Synchronisationsplattform soll nicht entwickelt werden.

**Abgrenzung:** QField als Erfassungs-App ist vorhanden und hier **nicht erneut Gegenstand einer Produktwahl**. Cloud- und Dateiübertragung sind **Lösungswege**, keine identischen Softwareprodukte; Kosten, IT-Sicherheit und fachliche Übernahme werden dennoch nach derselben Methodik verglichen.

## 2. Besondere Anforderungen

- **Muss:** Daten und Anhänge in beiden Richtungen ohne unbemerkten Verlust oder Fehlzuordnung übertragen.
- **Muss:** Zugriffsrechte, Datensicherheit und kontrollierte fachliche Übernahme gewährleisten; Synchronisation gilt nicht als Freigabe.
- **Soll:** Gelegentlich offline erfassen; für Mitarbeiter mit wenig GIS-Erfahrung einfach bedienbar.
- **Offen:** Online/Offline-Anteile, Konfliktbehandlung, VPN/registrierte Geräte, tatsächliche Cloud-Funktionen und Transferhäufigkeit.

| Frage | Lokaler Datei-/USB-Transfer | Gehostete QFieldCloud | Selbst gehostete QFieldCloud |
|---|---|---|---|
| Hin-/Rücktransfer mit Geometrien, Attributen und Anhängen | ? | ? | ? |
| Sicherer kontrollierter Umgang mit Konflikten und Zugriff | ? | ? | ? |

**Hinweis:** `?` bedeutet **noch nicht nachgewiesen**, nicht `nicht erfüllt`.

## 3. Kandidaten (noch keine Auswahl)

| Kandidat | Charakter / Prüfansatz | Ausgangsquelle |
|---|---|---|
| **Lokaler Datei-/USB-Transfer** | QField-Projekte lokal halten und kontrolliert per Kabel übertragen. | [Projekt-/Herstellerdokumentation](https://docs.qfield.org/) |
| **Gehostete QFieldCloud** | Vom Anbieter betriebener Cloud-Dienst für Projekt- und Datenabgleich. | [Projekt-/Herstellerdokumentation](https://qfield.cloud/pricing) |
| **Selbst gehostete QFieldCloud** | Eigene Betriebsvariante des offenen QFieldCloud-Backends. | [Projekt-/Herstellerdokumentation](https://docs.qfield.org/reference/qfieldcloud/self_hosted/) |

## 4. Vergleichsmatrix

**Bewertung noch nicht begonnen:** Alle bisherigen Punkte- und Produktstandfelder waren `?` bzw. `n. a.`; eine ausgefüllte Matrix würde hier fälschlich eine belastbare Vergleichsstufe suggerieren. Ein lokaler USB-Dateitransfer ist **ein Verfahren, kein Softwareprodukt**. QFieldCloud-Varianten werden anhand echter Pilotfälle, Rechte und Betriebskosten verglichen.

Sobald ein bestätigter Pilotbedarf eine echte Auswahl erforderlich macht, die [standardisierte Vergleichsmatrix](VORLAGE.md#4-vergleichsmatrix) nach [Methodik](BEWERTUNGSMETHODIK.md) mit aktuellem Produkt-/Versionsstand, nachgewiesenen Muss-Kriterien, Quellen und Bewertungsstichtag erstellen. **Keine Rangfolge oder Gesamtpunktzahl ohne Belege.**

## 5. Vor- und Nachteile – vorläufige Prüfhypothesen

**Lokaler Datei-/USB-Transfer:** Ohne zusätzliche Cloudplattform könnten Abhängigkeiten und externe Dienste geringer ausfallen; der manuelle Prozess kann fehleranfällig oder umständlich sein. **Noch zu verifizieren:** Praxistest der Pakete/Anhänge, Konflikte, Wiederholbarkeit und Bedienung.

**Gehostete QFieldCloud:** Zentrale Synchronisationsfunktionen können den Datenaustausch erleichtern; mögliche laufende Kosten, Datenschutz- und Zugangsvorgaben wären zu klären. **Noch zu verifizieren:** Aktueller Funktions-/Preistarif, Unternehmensfreigabe, Datenstandort, Rechte und Offline-Fall.

**Selbst gehostete QFieldCloud:** Mehr Kontrolle über Infrastruktur/Daten kann ein Vorteil sein; zusätzliche Betriebs-, Update- und Supportaufgaben können den MVP überladen. **Noch zu verifizieren:** IT-Kapazität, Komponenten/Abhängigkeiten, Restore, Zugriff und laufender Betrieb.

**Lizenz-/Kostenabgrenzung:** Die [QField-App](https://docs.qfield.org/get-started/license/) ist kostenlos. Bei [gehosteter QFieldCloud](https://qfield.cloud/pricing) sind abhängig von Tarif und benötigtem Funktionsumfang Gebühren möglich; die selbst gehostete Open-Source-Variante benötigt eigene Administration, Serverressourcen und Sicherung. Lokaler Datei-/USB-Transfer kann ohne zusätzliches Cloudabonnement auskommen, verursacht aber manuellen Prozessaufwand. Weder ein bezahlter Dienst noch Self-Hosting ist beschlossen.

## 6. Bewertung und Empfehlung

**Aktueller Status: Noch keine belastbare Produktempfehlung.** Der Vergleich muss mit derselben QField-Pilotkonfiguration stattfinden; keine Cloudvariante allein aufgrund von Komfort vorab festlegen.

**Nächster Schritt:** Mit BB-01 bis BB-03 und realistischen freigegebenen Testdaten beide Übertragungsrichtungen inklusive Offline-Fall, Anhängen und Konflikten nachvollziehbar durchspielen; IT klärt Sicherheit und ggf. Cloud-/Hostingkosten.

## 7. Quellen und Stand

- [QField-Dokumentation](https://docs.qfield.org/) – offizielle Dokumentation; mobile Projekte und Austauschwege
- [QFieldCloud – Preismodelle](https://qfield.cloud/pricing) – Anbieterquelle; mögliche gehostete Leistungen und Kosten; Tarifstand prüfen
- [QFieldCloud – Self-Hosting](https://docs.qfield.org/reference/qfieldcloud/self_hosted/) – offizielle Doku; Eigenbetrieb des Open-Source-Backends
- [Pilotkonkretisierung VIC-GDI](../05_PILOTKONKRETISIERUNG.md#mobile-erfassung-und-datenaustausch) – intern; bestehende Praxis und Testanforderungen

**Quellenstand:** Ausgangslinks am 04.11.2026 zusammengestellt; **keine vollständige Release-, Lizenz-, Sicherheits- oder Praxistestprüfung**. Unabhängige Bewertungen und Erfahrungsberichte sowie ggf. PoC-Ergebnisse werden beim echten Vergleich mit Version und Datum ergänzt.
