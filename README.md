# VIC-GDI

**Status:** Interner Arbeitsentwurf · **Organisationsentscheidung [A39](docs/04_ENTSCHEIDUNGEN.md#a39) offen** · keine formale Freigabe durch IT oder Geschäftsführung.

## Wozu VIC-GDI?

Viele Informationen in unseren Projekten haben einen Ort: Leitungsverläufe, Grundstücke, Vermessungspunkte oder Bauwerke. Heute liegen solche Informationen teils an unterschiedlichen Stellen. Wer sie verwenden möchte, muss zunächst den richtigen Stand finden und wissen, wer dafür verantwortlich ist.

**VIC-GDI soll eine gemeinsame Grundlage für diese Informationen schaffen:** Geeignete Daten werden nachvollziehbar gepflegt, sind leichter auffindbar und können von berechtigten Mitarbeitenden wiederverwendet werden. Eine **Geodateninfrastruktur (GDI)** ist deshalb **kein einzelnes Programm**, sondern das Zusammenspiel von Datenhaltung, Auffindbarkeit, Bereitstellung und verlässlichem Betrieb. [Einfach erklärte Funktionsbereiche mit Schaubild](docs/01_PROJEKTKONZEPT.md#was-ist-eine-geodateninfrastruktur--und-wie-funktioniert-sie).

Die Initiative geht vom GIS-Team und beteiligten Fachkollegen aus. Für die Facharbeit sind QGIS, für andere Mitarbeitende einfache Browserkarten und für geeignete Aufgaben mobile Abläufe vorgesehen. Die GDI ergänzt bestehende CAD-, BIM- und Fachsysteme; sie ersetzt diese nicht. **Die formale Freigabe von Umsetzung, Ressourcen und Betrieb steht noch aus.**

**Konkrete Einstiegsmöglichkeiten:** Die Baubetreuung übernimmt mobil erfasste Leitungsverläufe nach fachlicher Prüfung oder wertet erfasste Mengen aus; die Verkehrsanlagenplanung nutzt geeignete Daten projektübergreifend aus einem gemeinsamen Bestand. Die Piloten erschließen solche Vorteile **schrittweise in der Praxis**. Konkrete Zeit- und Kosteneinsparungen werden nicht ohne belastbare Zahlen behauptet. [Fachliche Begründung und Praxisbeispiele](docs/01_PROJEKTKONZEPT.md#warum-wir-vic-gdi-einführen-wollen).

## Was aktuell geklärt werden muss: A39

**Nicht der grundsätzliche Nutzen einer GDI, sondern ihre konkrete Einführung ist jetzt zu entscheiden.** Für eine belastbare Pilot-/Umsetzungsfreigabe erarbeiten Geschäftsführung, IT und GIS-Team eine tragfähige Richtung für **Umsetzung, Wissensaufbau und Dauerbetrieb**. Interner Aufbau, gemeinsame Umsetzung und externe Leistungen sind ebenso offene Varianten wie die eigenständige **Hosting-/Bezugsdimension H1–H4**: vorhandene VIC-Server, **gemieteter Server mit eigener GDI**, Managed Hosting oder eine **GDI as a Service (GDIaaS)**-Plattform. Auch Zuständigkeiten, verfügbare Personentage, fachliche Anforderungen und Kosten müssen realistisch geklärt werden. Die Entscheidung über vorbereitende Ressourcen ist von einer späteren verbindlichen Pilotfreigabe zu unterscheiden.

| Für wen? | Einstiegslektüre und nächste Frage |
|---|---|
| **Geschäftsführung** | [GF-Briefing](docs/BRIEFING_GESCHAEFTSFUEHRUNG.md): Warum das Projekt? Welche Ressourcen für Vorbereitung und spätere Umsetzung? |
| **IT** | [IT-Briefing](docs/BRIEFING_IT.md): Welche Infrastruktur, Kompetenzen, Sicherheits- und Betriebsverantwortung sind tragfähig? |
| **GF + IT + GIS-Team** | [A39-Modellvergleich](docs/06_UMSETZUNGS_UND_BETRIEBSMODELLE.md): Wer setzt um, wie sichern wir Wissen, wer betreibt, und wo wird die GDI gehostet? |

**Kostenprinzip:** Der geplante GDI-Kern verwendet **freie Open-Source-Software ohne zusätzliche Softwarelizenzgebühren**. Auch Proxmox VE als Virtualisierungsplattform ist ohne zwingende kostenpflichtige Subskription nutzbar. Das macht **Aufbau, Arbeitszeit, Schulungen, Betrieb, Infrastruktur und optionale externe Dienste nicht kostenlos**. [Komponenten und Lizenzquellen](docs/software/README.md#lizenz--und-kostenüberblick-gdi-kern) · [wirtschaftlicher Gesamtrahmen](docs/06_UMSETZUNGS_UND_BETRIEBSMODELLE.md#kostenrahmen-und-lizenzabgrenzung).

## Fachliches und technisches Konzept (gezielt vertiefen)

1. [Projektkonzept mit GDI-Einführung und acht Projektgrundsätzen](docs/01_PROJEKTKONZEPT.md) – verständliches Grundmodell, Motivation, Leitplanken und Piloten.
2. [Anforderungen](docs/02_ANFORDERUNGEN.md) – fachlicher und nichtfunktionaler Rahmen.
3. [Pilotkonkretisierung](docs/05_PILOTKONKRETISIERUNG.md) – tatsächliche Praxis, Vorschläge und noch zu erhebende Anforderungen.
4. [Roadmap](docs/07_ROADMAP.md) – Vorbereitung, Freigabeschritte und gestaffelte Einführung.
5. [Offene Punkte](docs/08_OFFENE_PUNKTE.md) – **nach Entscheidungszeitpunkt priorisierte** Prüfaufträge.
6. [Architektur](docs/03_ARCHITEKTUR.md) – logisches Zielbild und technische Leitplanken, keine Implementierungsfreigabe.
7. [Festlegungs- und Entscheidungsregister A01–A39](docs/04_ENTSCHEIDUNGEN.md) – stabile Kennungen, Kategorien, Status und Prüfvorbehalte.

## Technische Vertiefung und Nachschlagen

- [Softwarekandidaten und Lizenzüberblick](docs/software/README.md) – Prüfgrundlagen ohne vorgetäuschte Punktbewertungen; vollständiger Vergleich erst bei Bedarf.
- [Glossar](docs/ANHANG_A_GLOSSAR.md) – Fachbegriffe und Abkürzungen.
- [Dokumentationspflege](docs/ANHANG_B_DOKUMENTATIONSPFLEGE.md) – Regeln für konsistente, wartbare Dokumente.

**Leseregel:** Die technischen Dokumente sichern bereits erarbeitete Anforderungen und Prüfvarianten. Nicht alle Detailfragen sind jetzt zu entscheiden; **eine Vorzugsvariante ist kein IT-/GF-Beschluss**. Entscheidungsstatus wird ausschließlich im [Register](docs/04_ENTSCHEIDUNGEN.md) geführt.
