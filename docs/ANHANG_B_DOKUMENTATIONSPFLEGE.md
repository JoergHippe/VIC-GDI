# Dokumentationspflege

## Pflegegrundsätze

1. **Keine Empfehlung als Beschluss ausgeben.** Status: Beschlossen; Grundsatz beschlossen – Detail offen; Zurückgestellt; Offen.
2. Das [Entscheidungsregister](04_ENTSCHEIDUNGEN.md) hält Beschluss und Begründung fest. Die [Anforderungen](02_ANFORDERUNGEN.md) beschreiben das **Was**, die [Architektur](03_ARCHITEKTUR.md) das **Wie**. Zielgruppensichten verweisen auf diese führenden Stellen.
3. Bei jeder Änderung Auswirkungen auf andere Dokumente prüfen und betroffene Dateien im selben Änderungspaket aktualisieren.
4. Nicht beschlossene Varianten bleiben sichtbar; technische Details mit IT abstimmen.
5. Nur bei tatsächlichem Bedarf zusätzliche Dokumente, Verzeichnisse oder Prozesse einführen.
6. Keine Zugangsdaten, personenbezogenen Daten oder produktiven Geodaten in [Git](ANHANG_A_GLOSSAR.md#git) versionieren.
7. Fachbegriffe, Abkürzungen und Produkte auf jeder Seite beim ersten Auftreten zum [Glossar](ANHANG_A_GLOSSAR.md) verlinken. Allgemein bekannte Begriffe wie Windows, Linux, Microsoft 365, SharePoint und OneDrive voraussetzen. Bei unklarer Aufnahme ins Glossar nachfragen. Für Produkte offizielle Projektseiten oder Herstellerdokumentation verwenden.
8. Kleine, thematisch nachvollziehbare Commits; `main` ist zunächst ausreichend.
9. Aktuelle Dokumente halten geltende Beschlüsse samt Begründungen, den bekannten Ist-Stand und offene Aufgaben fest. Abgelöste Zwischenstände und abgeschlossene Dokumentationsreviews sind im Git-Verlauf nachvollziehbar.
10. Jede Nennung einer Architekturentscheidungs-ID direkt mit der Zeile im Entscheidungsregister verlinken. Bei Bereichen beide Endpunkte verlinken. Einen konkreten Prüfauftrag zusätzlich über seinen Abschnitt verlinken.

## Softwarebewertungen

Für noch offene Produktauswahlen ist [`docs/software/`](software/README.md) der einheitliche Bewertungsbereich. Alle Kategorie-Dateien folgen der [gemeinsamen Methodik](software/BEWERTUNGSMETHODIK.md) und [Vorlage](software/VORLAGE.md): klare Anforderungen, Muss-Prüfung, begrenzte Kandidatenliste, standardisierte Vergleichsmatrix, belegte Vor-/Nachteile und eine als solche gekennzeichnete Empfehlung bzw. offener Prüfauftrag. **Unbekannte Aussagen bleiben `?`; fiktive Beispielwerte dürfen nie als echte Bewertung oder Entscheidung übernommen werden.**

Kandidaten, deren Funktionsumfang bereits durch vorhandene Software abgedeckt werden könnte, und der Verzicht auf weitere Dienste sind mitzuberücksichtigen. Externe Bewertungen mit Datum, Version und Übertragbarkeit belegen. Neue Kategorien nur bei tatsächlich offenem Softwareauswahlbedarf anlegen. Verbindliche Beschlüsse gehören weiterhin ausschließlich ins [Entscheidungsregister](04_ENTSCHEIDUNGEN.md), nicht in einen zweiten Beschlusskatalog.

## Diagramme

Architektur- und Ablaufdiagramme werden bei erkennbarem Verständlichkeitsgewinn als **Mermaid-Quelltext direkt in den fachlich zuständigen Markdown-Dokumenten** gepflegt (GitHub-Darstellung, im Repository versionierbar). Beschlossene Beziehungen, bevorzugte Kandidaten und offene Prüfvarianten sind in Diagramm und Begleittext klar zu unterscheiden. **In der Konzeptphase bewusst einfach halten:** eine Kernaussage je Diagramm, möglichst nur 5–7 Hauptelemente, klare Leserichtung, wenige Pfeile und generalisierte Gruppen statt technischer Einzelkomponenten. Bei zu viel Detail lieber Text oder ein späteres separates Diagramm verwenden. Keine zusätzliche Diagrammdatei oder Grafikduplikate ohne konkreten Bedarf; Diagramme bei inhaltlichen Änderungen mitpflegen.
