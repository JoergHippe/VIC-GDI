# VIC-GDI

**Status:** Interner Arbeitsentwurf · Stand: 2026-11-03 · keine formale Freigabe durch IT oder Geschäftsführung.

VIC-GDI ist die geplante unternehmensweite, fachbereichsneutrale Geodateninfrastruktur für die gemeinsame, sichere und wartbare Nutzung von Geodaten in der Infrastrukturplanung. Die ersten Piloten sind Baubetreuung/Bauüberwachung und Verkehrsanlagenplanung.

## Dokumentation

- [Glossar](docs/GLOSSAR.md) – Fachbegriffe und Abkürzungen
- [Projektkonzept](docs/PROJEKTKONZEPT.md) – Ziele, Grenzen, Pilotbereiche
- [Management](docs/MANAGEMENT.md) – Nutzen, Ressourcen, Risiken
- [Anforderungen](docs/ANFORDERUNGEN.md) – fachliche und nichtfunktionale Anforderungen
- [Architektur](docs/ARCHITEKTUR.md) – konsolidierter technischer Sollzustand
- [Entscheidungen](docs/ENTSCHEIDUNGEN.md) – A01–A38, Status und Begründungen
- [Offene Punkte](docs/OFFENE_PUNKTE.md) – Rückstellungen, IT-Abstimmungen, PoCs
- [Roadmap](docs/ROADMAP.md) – MVP, Piloten, Einführungsfolge
- [Betrieb und IT](docs/BETRIEB_UND_IT.md) – Betriebsperspektive und Zuständigkeiten

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
