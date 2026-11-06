# VIC-GDI

**Status:** Interner Arbeitsentwurf

## Wozu VIC-GDI?

Viele Informationen in unseren Projekten haben einen räumlichen Bezug: Kataster, Schutzgebiete, Leitungsverläufe, Vermessungspunkte oder Bauwerke. Heute liegen solche Informationen verteilt an unterschiedlichen Stellen. Wer sie verwenden möchte, muss zunächst den richtigen Speicherort, den korrekten Stand finden und wissen, wer dafür verantwortlich ist.

**VIC-GDI soll eine gemeinsame Grundlage für diese Informationen schaffen:** Geeignete Daten werden nachvollziehbar gepflegt, sind leichter auffindbar und können von berechtigten Mitarbeitenden verwendet werden. Eine **Geodateninfrastruktur (GDI)** ist deshalb **kein einzelnes Programm**, sondern das Zusammenspiel von Datenhaltung, Auffindbarkeit, Bereitstellung und verlässlichem Betrieb. [Einfach erklärte Funktionsbereiche mit Schaubild](docs/01_PROJEKTKONZEPT.md#was-ist-eine-geodateninfrastruktur--und-wie-funktioniert-sie).

Die Initiative zum Aufbau einer GDI geht vom GIS-Team aus. Für die Facharbeit sind QGIS, für andere Mitarbeitende einfache browserbasierende Kartenviewer-/editoren und für geeignete Aufgaben mobile Abläufe vorgesehen. Die GDI ergänzt bestehende CAD-, BIM- und Fachsysteme, sie ersetzt diese nicht.

**Konkrete Einstiegsmöglichkeiten:** Die Baubetreuung übernimmt mobil erfasste Leitungsverläufe oder wertet erfasste Mengen aus. Die Verkehrsanlagenplanung nutzt geeignete Daten projektübergreifend aus einem gemeinsamen Bestand und wertet diese aus und integriert sie in ihre Pläne. Vorgesehene Piloten erschließen solche Vorteile **schrittweise in der Praxis**. [Fachliche Begründung und Praxisbeispiele](docs/01_PROJEKTKONZEPT.md#warum-wir-vic-gdi-einführen-wollen).

## Was aktuell geklärt werden muss

**Nicht der grundsätzliche Nutzen einer GDI, sondern ihre konkrete Einführung ist zu entscheiden.** Für eine belastbare Pilot-/Umsetzungsfreigabe erarbeiten Geschäftsführung, IT und GIS-Team eine tragfähige Richtung für **Umsetzung, Wissensaufbau und Dauerbetrieb**. Interner Aufbau, Umsetzung und externe Leistungen sind offen und sind zusammen zu klären. Auch Zuständigkeiten, verfügbare Personentage, fachliche Anforderungen und Kosten müssen geklärt werden.

| Für wen? | Einstiegslektüre und nächste Frage |
|---|---|
| **Geschäftsführung** | [GF-Briefing](docs/BRIEFING_GESCHAEFTSFUEHRUNG.md): Warum das Projekt? Welche Ressourcen für Vorbereitung und spätere Umsetzung? |
| **IT** | [IT-Briefing](docs/BRIEFING_IT.md): Welche Infrastruktur, Kompetenzen, Sicherheits- und Betriebsverantwortung sind tragfähig? |
| **GF + IT + GIS-Team** | [A39-Modellvergleich](docs/06_UMSETZUNGS_UND_BETRIEBSMODELLE.md): Wer setzt um, wie sichern wir Wissen, wer betreibt, und wo wird die GDI gehostet? |

**Kostenprinzip:** Der geplante GDI-Stack verwendet **freie Open-Source-Software ohne zusätzliche Softwarelizenzgebühren**. Das macht **Aufbau, Arbeitszeit, Schulungen, Betrieb, Infrastruktur und optionale externe Dienste nicht kostenlos**. [Komponenten und Lizenzquellen](docs/software/README.md#lizenz--und-kostenüberblick-gdi-kern) · [wirtschaftlicher Gesamtrahmen](docs/06_UMSETZUNGS_UND_BETRIEBSMODELLE.md#kostenrahmen-und-lizenzabgrenzung).

## Fachliches und technisches Konzept

1. [Projektkonzept mit GDI-Einführung und acht Projektgrundsätzen](docs/01_PROJEKTKONZEPT.md) – verständliches Grundmodell, Motivation, Leitplanken und Piloten.
2. [Anforderungen](docs/02_ANFORDERUNGEN.md) – fachlicher und nichtfunktionaler Rahmen.
3. [Pilotkonkretisierung](docs/05_PILOTKONKRETISIERUNG.md) – tatsächliche Praxis, Vorschläge und noch zu erhebende Anforderungen.
4. [Roadmap](docs/07_ROADMAP.md) – Vorbereitung, Freigabeschritte und gestaffelte Einführung.
5. [Offene Punkte](docs/08_OFFENE_PUNKTE.md) – **nach Entscheidungszeitpunkt priorisierte** Prüfaufträge.
6. [Architektur](docs/03_ARCHITEKTUR.md) – logisches Zielbild und technische Leitplanken, keine Implementierungsfreigabe.
7. [Festlegungs- und Entscheidungsregister A01–A39](docs/04_ENTSCHEIDUNGEN.md) – stabile Kennungen, Kategorien, Status und Prüfvorbehalte.

## Technische Vertiefung und Glossar

- [Softwarekandidaten und Lizenzüberblick](docs/software/README.md) – Prüfgrundlagen ohne vorgetäuschte Punktbewertungen; vollständiger Vergleich erst bei Bedarf.
- [Glossar](docs/ANHANG_A_GLOSSAR.md) – Fachbegriffe und Abkürzungen.
- [Dokumentationspflege](docs/ANHANG_B_DOKUMENTATIONSPFLEGE.md) – Regeln für konsistente, wartbare Dokumente.

**Leseregel:** Die technischen Dokumente sichern bereits erarbeitete Anforderungen und Prüfvarianten. Nicht alle Detailfragen sind jetzt zu entscheiden; **eine Vorzugsvariante ist kein IT-/GF-Beschluss**. Entscheidungsstatus wird ausschließlich im [Register](docs/04_ENTSCHEIDUNGEN.md) geführt.
