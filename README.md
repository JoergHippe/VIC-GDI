# VIC-GDI

**Status:** Interner Arbeitsentwurf · Stand: 2026-11-03 · keine formale Freigabe durch IT oder Geschäftsführung.

VIC-GDI ist die geplante unternehmensweite, fachbereichsneutrale Geodateninfrastruktur für die gemeinsame, sichere und wartbare Nutzung von Geodaten in der Infrastrukturplanung. Die ersten Piloten sind Baubetreuung/Bauüberwachung und Verkehrsanlagenplanung.

## Gesprächsunterlagen

- [IT-Briefing](docs/BETRIEB_UND_IT.md) – GDI-Grundlagen, Infrastruktur, Betrieb, Agenda und Fragen
- [Geschäftsführungs-Briefing](docs/MANAGEMENT.md) – Nutzen, Piloten, Ressourcen und Beschlussbedarf

## Konzept und Referenz

- [Glossar](docs/GLOSSAR.md) – Fachbegriffe und Abkürzungen
- [Projektkonzept](docs/PROJEKTKONZEPT.md) – Ziele, Grenzen, Pilotbereiche
- [Anforderungen](docs/ANFORDERUNGEN.md) – fachliche und nichtfunktionale Anforderungen
- [Architektur](docs/ARCHITEKTUR.md) – konsolidierter technischer Sollzustand
- [Entscheidungen](docs/ENTSCHEIDUNGEN.md) – A01–A38, Status, Begründungen und Prüfvorbehalte
- [Offene Punkte](docs/OFFENE_PUNKTE.md) – Rückstellungen, IT-Abstimmungen, PoCs
- [Pilotkonkretisierung](docs/PILOTKONKRETISIERUNG.md) – Erhebung und Prüfhypothesen der beiden Pilotbereiche
- [Roadmap](docs/ROADMAP.md) – MVP, Piloten, Einführungsfolge

## Pflegegrundsätze

1. **Keine Empfehlung als Beschluss ausgeben.** Status: Beschlossen; Grundsatz beschlossen – Detail offen; Zurückgestellt; Offen.
2. Das Entscheidungsregister hält Beschluss und Begründung fest; Anforderungen beschreiben das **Was**, Architektur das **Wie**. Zielgruppensichten verweisen auf diese führenden Stellen.
3. Bei jeder Änderung Auswirkungen auf andere Dokumente prüfen und betroffene Dateien im selben Änderungspaket aktualisieren.
4. Nicht beschlossene Varianten bleiben sichtbar; technische Details mit IT abstimmen.
5. Nur bei tatsächlichem Bedarf zusätzliche Dokumente, Verzeichnisse oder Prozesse einführen.
6. Keine Zugangsdaten, personenbezogenen Daten oder produktiven Geodaten in Git versionieren.
7. Fachbegriffe beim ersten Auftreten je Dokument zum [Glossar](docs/GLOSSAR.md) verlinken.
8. Kleine, thematisch nachvollziehbare Commits; `main` ist zunächst ausreichend.

**Quellenlage:** Erstkonsolidierung aus den bisherigen Architekturgesprächen A01–A38. Wo kein detailliertes Entscheidungsprotokoll vorliegt, sind die Aussagen bewusst auf die gesicherten Grundsätze begrenzt. Die Dokumente sind keine Implementierungs- oder Freigabenachweise.

## Diagramme

Architektur- und Ablaufdiagramme werden bei erkennbarem Verständlichkeitsgewinn als **Mermaid-Quelltext direkt in den fachlich zuständigen Markdown-Dokumenten** gepflegt (GitHub-Darstellung, im Repository versionierbar). Beschlossene Beziehungen, bevorzugte Kandidaten und offene Prüfvarianten sind in Diagramm und Begleittext klar zu unterscheiden. **In der Konzeptphase bewusst einfach halten:** eine Kernaussage je Diagramm, möglichst nur 5–7 Hauptelemente, klare Leserichtung, wenige Pfeile und generalisierte Gruppen statt technischer Einzelkomponenten. Bei zu viel Detail lieber Text oder ein späteres separates Diagramm verwenden. Keine zusätzliche Diagrammdatei oder Grafikduplikate ohne konkreten Bedarf; Diagramme bei inhaltlichen Änderungen mitpflegen.
