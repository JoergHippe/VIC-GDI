# Dokumentationspflege

## Pflegegrundsätze

1. **Keine Empfehlung als Beschluss ausgeben.** Status: Beschlossen; Grundsatz beschlossen – Detail offen; Zurückgestellt; Offen.
2. Das [Entscheidungsregister](04_ENTSCHEIDUNGEN.md) hält Beschluss und Begründung fest. Die [Anforderungen](02_ANFORDERUNGEN.md) beschreiben das **Was**, die [Architektur](03_ARCHITEKTUR.md) das **Wie**. Zielgruppensichten verweisen auf diese führenden Stellen.
3. Bei jeder Änderung Auswirkungen auf andere Dokumente prüfen und betroffene Dateien im selben Änderungspaket aktualisieren.
4. Nicht beschlossene Varianten bleiben sichtbar; technische Details mit IT abstimmen.
5. Nur bei tatsächlichem Bedarf zusätzliche Dokumente, Verzeichnisse oder Prozesse einführen.
6. Keine Zugangsdaten, personenbezogenen Daten oder produktiven Geodaten in Git versionieren.
7. Fachbegriffe beim ersten Auftreten je Dokument zum [Glossar](ANHANG_A_GLOSSAR.md) verlinken.
8. Kleine, thematisch nachvollziehbare Commits; `main` ist zunächst ausreichend.
9. Aktuelle Dokumente halten geltende Beschlüsse samt Begründungen, den bekannten Ist-Stand und offene Aufgaben fest. Abgelöste Zwischenstände und abgeschlossene Dokumentationsreviews sind im Git-Verlauf nachvollziehbar.

## Diagramme

Architektur- und Ablaufdiagramme werden bei erkennbarem Verständlichkeitsgewinn als **Mermaid-Quelltext direkt in den fachlich zuständigen Markdown-Dokumenten** gepflegt (GitHub-Darstellung, im Repository versionierbar). Beschlossene Beziehungen, bevorzugte Kandidaten und offene Prüfvarianten sind in Diagramm und Begleittext klar zu unterscheiden. **In der Konzeptphase bewusst einfach halten:** eine Kernaussage je Diagramm, möglichst nur 5–7 Hauptelemente, klare Leserichtung, wenige Pfeile und generalisierte Gruppen statt technischer Einzelkomponenten. Bei zu viel Detail lieber Text oder ein späteres separates Diagramm verwenden. Keine zusätzliche Diagrammdatei oder Grafikduplikate ohne konkreten Bedarf; Diagramme bei inhaltlichen Änderungen mitpflegen.
