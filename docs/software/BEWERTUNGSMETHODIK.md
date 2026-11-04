# Einheitliche Methodik für Softwarebewertungen

**Geltung:** Alle Dateien SW-01 bis SW-06. **Status:** Entwurf für Prüfung durch den Projektverantwortlichen.

## Ablauf und Entscheidungshygiene

1. **Bedarf zuerst:** Aufgabe, Nutzer, Pilotbezug und betroffene Schnittstellen kurz beschreiben. „Keine zusätzliche Software“ bzw. vorhandene Werkzeuge als Kandidat zulassen, soweit sachlich möglich.
2. **Muss-Kriterien separat:** Als `erfüllt`, `nicht erfüllt` oder `?` bewerten. Ein belegtes, nicht erfülltes Muss-Kriterium scheidet den Kandidaten aus; ein offenes Muss-Kriterium verhindert eine endgültige Empfehlung.
3. **Kandidaten begrenzen:** Zwei bis vier ernsthaft geeignete Varianten. Bei stark verschiedenen Lösungswegen (z. B. Cloud vs. USB) die Architektur-/Kostenfolgen ausdrücklich nennen.
4. **Einheitlicher Vergleich:** Die sechs übergreifenden Kriterien und zusätzlich **Produktalter, aktuelle stabile Version und Entwicklungsaktivität** verwenden; je Kategorie konkrete fachliche Prüfhinweise ergänzen, **ohne die Gewichte stillschweigend zu verändern**.
5. **Belege und Nachteile:** Nach jedem Vergleich textlich die wichtigsten Stärken, Schwächen, Ausschlussgründe und offene Risiken nennen.
6. **Ergebnisstatus:** `offen` / `vorläufig empfohlen` / `durch IT/Pilot zu prüfen` / `beschlossen`. **Nur das Entscheidungsregister** kann eine Beschlusslage belegen.

## Produktstand und Entwicklungsaktivität (in jeder Vergleichsmatrix)

Diese drei **Sachangaben** stehen oberhalb der gewichteten Bewertungszeilen. Sie erhalten **keine eigenen Punkte oder zusätzlichen Gewichte**; ihre Bedeutung fließt begründet in **Reife und Zukunftsfähigkeit** (ggf. Betrieb/Sicherheit) ein.

| Angabe | Einheitliche Erfassung | Beleg |
|---|---|---|
| **Erstveröffentlichung / seit (Jahr)** | Möglichst erstes öffentliches Release der tatsächlich bewerteten Software; bei Forks die eigenständige Produktgeschichte angeben, nicht nur die Vorgeschichte des Ursprungsprojekts. | Projektchronik, dokumentiertes erstes Release, Archiv/Repository |
| **Aktuelle stabile Version (Datum)** | Versionsnummer **und Releasedatum**, soweit veröffentlicht; LTS/LTR und Rolling-/Cloud-Releases klar unterscheiden. Keine Betaversion als stabile Version ausgeben. | Offizielle Release Notes, Changelog, Tag mit Veröffentlichung |
| **Entwicklungsaktivität (12 Monate)** | Soweit ermittelbar Anzahl stabiler Releases im zurückliegenden 12-Monats-Fenster und kurze qualitative Einordnung; Sicherheitsfixes, Wartung, reale Beiträge und bekannte Unterbrechungen mit berücksichtigen. | Releasehistorie, Maintainer-Updates, Security Advisories, ggf. Issue-Tracker |

**Bewertungsstichtag** je Produktvergleich angeben; die Version ist nur **zu diesem Stichtag** aktuell. Ein hoher Release-Takt ist **nicht automatisch** ein Qualitätsmerkmal. Reife, Wartung und langfristige Zukunftsfähigkeit können auch mit seltenen, aber gut gepflegten stabilen Releases hoch sein. Commits, Issues und Releasezahlen sind lediglich Indikatoren, keine mechanische Bewertung. Bei Produkten ohne öffentliches Versionsschema „laufend bereitgestellt / Version nicht veröffentlicht“ verwenden, **falls belegt**. Bei Lösungswegen ohne eigenes Softwareprodukt (z. B. USB-Transfer, Eigenlösung ohne Implementierung) `n. a.` eintragen; bei nicht recherchierten Angaben `?`.

## Bewertungsraster (identisch für alle Kategorien)

| Bewertungsdimension | Gewicht | Was geprüft wird |
|---|---:|---|
| Fachliche und funktionale Eignung | 30 % | Bestätigte Pilotabläufe, Bedienbarkeit, gewünschte Funktionen ohne überflüssige Komplexität |
| Integration und Interoperabilität | 20 % | QGIS/PostGIS, OGC/andere passende Schnittstellen, bestehende IT und Datenflüsse |
| Sicherheit und Berechtigungen | 15 % | Zugriff auf allen direkten Wegen, Authentifizierung, Sicherheitsupdates, Datenhoheit |
| Betrieb und Wartbarkeit | 15 % | Deployment, Updates, Backup/Restore, Monitoring, IT-Kompetenz, Fehlersuche |
| Reife und Zukunftsfähigkeit | 10 % | Wartung/Releasepflege, Projektaktivität, Community, Migrationsfähigkeit, Lock-in |
| Gesamtkosten und Lizenzierung | 10 % | Lizenzpflichten, Support, Einführungs-/Betriebsaufwand, Infrastruktur-/Cloudkosten |
| **Summe** | **100 %** | |

**Skala je Dimension:** `0` = ungeeignet, `1` = nur mit erheblichen Nachteilen, `2` = geeignet mit handhabbaren Einschränkungen, `3` = gut passend, `?` = noch nicht belastbar beurteilt.

**Gesamtwert (optional, erst bei vollständig belegten Dimensionen und erfüllten Muss-Kriterien):** `Σ(Gewicht × Punktzahl / 3)` ergibt maximal 100 Punkte. Keine Rangliste oder Gesamtpunktzahl bei `?` bzw. offenen Muss-Kriterien. **Eine kleine Punktdifferenz ersetzt keine fachliche Abwägung.** Faktoren können projektspezifisch begründet angepasst werden, aber nur **vor** der Bewertung und nachvollziehbar für alle Kandidaten einer Kategorie.

## Quellen und Evidenz

| Evidenzstand | Bedeutung | Typische Belege |
|---|---|---|
| `E0` | Annahme / offen | Ungeprüfte Aussage, ungeklärte Version oder Lizenz |
| `E1` | Dokumentiert | Offizielle Produkt-/Entwicklerdokumentation, Changelog, Lizenz, Security Policy |
| `E2` | Extern plausibilisiert | Unabhängige technische Bewertung, OSGeo-/Community-Material, nachvollziehbarer Erfahrungsbericht |
| `E3` | Im VIC-Pilot getestet | Reproduzierbarer Testfall mit Version, Konfiguration, Ergebnis und Datum |

**Quellenregeln:** Für wichtige Aussagen möglichst die konkrete offizielle Doku/Version verlinken; unabhängige Reviews und Issue-Tracker ergänzen, aber nicht mit Herstelleraussagen gleichsetzen. Release-, Sicherheits- und Lizenzinformationen datieren; keine Sterne, Scores oder Benchmarks ohne belastbare Quelle. Ein fehlender unabhängiger Bericht wird als `noch nicht vorhanden` notiert, nicht erfunden.

**Lizenzprinzip:** Open Source und keine zusätzlichen Lizenzgebühren sind das Ziel des GDI-Kerns ([Kostenrahmen](../ANHANG_C_SOFTWARE_LIZENZEN_KOSTEN.md)). Proprietäre oder gehostete Alternativen nur bei nachweislichem Zusatznutzen und mit transparenten Folgekosten betrachten. **„Kostenlos“ bedeutet nicht „ohne Betriebs-/Personalaufwand“.**

## Einheitliche Dokumentstruktur

1. Zweck und Abgrenzung
2. Spezifische Anforderungen / Muss-Prüfung
3. Kandidaten und Quellen
4. Vergleichsmatrix (drei Sachangaben zu Produktstand/Entwicklungsaktivität, sechs gewichtete Dimensionen, Evidenz)
5. Vor- und Nachteile je Kandidat (kurz, sachlich, mit Belegen)
6. Bewertung und vorläufige Empfehlung / offener Prüfauftrag
7. Quellen-/Aktualitätsverzeichnis

Siehe die [Vorlage](VORLAGE.md). Der [Mustervergleich](BEISPIEL_DUMMY.md) zeigt **fiktive Bewertungen** und darf nicht als Produktentscheidung übernommen werden.
