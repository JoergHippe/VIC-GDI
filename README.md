# VIC-GDI

**Status:** Interner Arbeitsentwurf · **Organisationsentscheidung [A39](docs/04_ENTSCHEIDUNGEN.md#a39) offen** · keine formale Freigabe durch IT oder Geschäftsführung.

## Wozu VIC-GDI?

VIC-GDI ist die geplante unternehmensweite, fachbereichsneutrale [Geodateninfrastruktur](docs/ANHANG_A_GLOSSAR.md#gdi) für die VIC. Heute liegen Geodaten und QGIS-Projekte an unterschiedlichen Orten; geeignete gemeinsame Daten werden teils mehrfach geführt, und Aktualität, fachliche Zuständigkeit und Weitergabe können zusätzliche Abstimmung erfordern. Die GDI soll **verlässliche führende Datenbestände, geregelte Zugriffe und gemeinsame Nutzung** ermöglichen – durch QGIS am Arbeitsplatz, bei Bedarf über einfache Webkarten im Browser und in geeigneten mobilen Abläufen. Sie ergänzt vorhandene CAD-, BIM- und Fachsysteme, statt sie zu ersetzen.

**Konkrete Beispiele:** Die Baubetreuung prüft mobil erfasste Leitungsverläufe, oder ermittelt Mengen; die Verkehrsanlagenplanung soll geeignete Geodaten projektübergreifend verwenden. Das sind **Ziele für die Piloten**, keine bereits nachgewiesenen Einsparungen. [Ausführliche Ausgangslage, Praxisbeispiele, Nutzen und Grenzen](docs/01_PROJEKTKONZEPT.md#warum-wir-vic-gdi-einführen-wollen).

## Was aktuell geklärt werden muss: A39

**Vor einer belastbaren Pilot-/Umsetzungsfreigabe** müssen Geschäftsführung, IT und GIS-Team eine tragfähige Richtung für **Umsetzung, Wissensaufbau und Dauerbetrieb** erarbeiten. Interner Aufbau, gemeinsame Umsetzung und externe Leistungen sind weiterhin offene Varianten. Auch Zuständigkeiten, verfügbare Personentage, fachliche Anforderungen und Kosten müssen realistisch geklärt werden. Die Entscheidung über vorbereitende Ressourcen ist von einer späteren verbindlichen Pilotfreigabe zu unterscheiden.

| Für wen? | Einstiegslektüre und nächste Frage |
|---|---|
| **Geschäftsführung** | [GF-Briefing](docs/BRIEFING_GESCHAEFTSFUEHRUNG.md): Warum das Projekt? Welche Ressourcen für Vorbereitung und spätere Umsetzung? |
| **IT** | [IT-Briefing](docs/BRIEFING_IT.md): Welche Infrastruktur, Kompetenzen, Sicherheits- und Betriebsverantwortung sind tragfähig? |
| **GF + IT + GIS-Team** | [A39-Modellvergleich](docs/06_UMSETZUNGS_UND_BETRIEBSMODELLE.md): Wer setzt um, wie sichern wir Wissen, wer betreibt dauerhaft? |

**Kostenprinzip:** Der geplante GDI-Kern verwendet **freie Open-Source-Software ohne zusätzliche Softwarelizenzgebühren**. Auch Proxmox VE als Betriebssystemebene ist ohne zwingende kostenpflichtige Subskription nutzbar. Das macht **Aufbau, Arbeitszeit, Schulungen, Betrieb, Infrastruktur und optionale externe Dienste nicht kostenlos**. [Komponenten und Lizenzquellen](docs/software/README.md#lizenz--und-kostenüberblick-gdi-kern) · [wirtschaftlicher Gesamtrahmen](docs/06_UMSETZUNGS_UND_BETRIEBSMODELLE.md#kostenrahmen-und-lizenzabgrenzung).

## Fachliches und technisches Konzept (gezielt vertiefen)

1. [Projektkonzept](docs/01_PROJEKTKONZEPT.md) – Motivation, Ziele, Nutzen, Abgrenzung und Piloten.
2. [Anforderungen](docs/02_ANFORDERUNGEN.md) – fachlicher und nichtfunktionaler Rahmen.
3. [Pilotkonkretisierung](docs/05_PILOTKONKRETISIERUNG.md) – tatsächliche Praxis, Vorschläge und noch zu erhebende Anforderungen.
4. [Roadmap](docs/07_ROADMAP.md) – Vorbereitung, Freigabeschritte und gestaffelte Einführung.
5. [Offene Punkte](docs/08_OFFENE_PUNKTE.md) – **nach Entscheidungszeitpunkt priorisierte** Prüfaufträge.
6. [Architektur](docs/03_ARCHITEKTUR.md) – logisches Zielbild und technische Leitplanken, keine Implementierungsfreigabe.
7. [Entscheidungsregister A01–A39](docs/04_ENTSCHEIDUNGEN.md) – führender Ort für Status, Begründungen und Prüfvorbehalte.

## Technische Vertiefung und Nachschlagen

- [Softwarekandidaten, Lizenzüberblick und Bewertungen](docs/software/README.md) – Prüfgrundlagen, **keine endgültige Produktauswahl**.
- [Glossar](docs/ANHANG_A_GLOSSAR.md) – Fachbegriffe und Abkürzungen.
- [Dokumentationspflege](docs/ANHANG_B_DOKUMENTATIONSPFLEGE.md) – Regeln für konsistente, wartbare Dokumente.

**Leseregel:** Die technischen Dokumente sichern bereits erarbeitete Anforderungen und Prüfvarianten. Nicht alle Detailfragen sind jetzt zu entscheiden; **eine Vorzugsvariante ist kein IT-/GF-Beschluss**. Entscheidungsstatus wird ausschließlich im [Register](docs/04_ENTSCHEIDUNGEN.md) geführt.
