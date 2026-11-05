# Geschäftsführungs-Briefing – VIC-GDI

**Status:** Interner Arbeitsentwurf · Entscheidungsgrundlage, keine Kosten- oder Terminzusage.

## Zielbild

Für Straßen-, Brücken- und andere Infrastrukturprojekte benötigen Mitarbeitende Informationen mit Ortsbezug, beispielsweise Leitungsverläufe, Vermessungsdaten oder Projektgebiete. Diese Informationen sollen leichter auffindbar, verlässlich aktuell und für berechtigte Teams gemeinsam nutzbar werden – statt sie an mehreren Stellen unabhängig zu pflegen.

**Dafür soll VIC-GDI eine gemeinsame organisatorische und technische Grundlage schaffen.** Eine **Geodateninfrastruktur (GDI)** ist kein einzelnes Programm: Sie verbindet geordnete Datenhaltung, ein Verzeichnis zum Wiederfinden der Informationen, geeignete Zugriffswege und klare Verantwortlichkeiten. [Einfaches Schaubild und Erläuterung](01_PROJEKTKONZEPT.md#was-ist-eine-geodateninfrastruktur--und-wie-funktioniert-sie).

Das GIS-Team und beteiligte Fachkollegen schlagen eine **gestaffelte Einführung** in Baubetreuung und Verkehrsanlagenplanung vor. Bestehende Planungs- und Fachprogramme werden ergänzt, nicht ersetzt. **Umsetzung, Ressourcen und Betrieb sind noch von Geschäftsführung und IT zu entscheiden.**

## Warum das Vorhaben wichtig ist

Heute verteilen sich Geodaten und QGIS-Projekte auf unterschiedliche Speicherorte und fachliche Zuständigkeiten. Für vergleichbare Aufgaben werden teils Daten kopiert und projektweise weiterbearbeitet. Das kann die Suche nach dem richtigen Stand, die Abstimmung zwischen Beteiligten und die Weitergabe von Informationen erschweren. In der Baubetreuung ist außerdem die Nutzung synchronisierter Ordner für führende GIS-Arbeitsdaten ein konkreter Verbesserungsansatz.

**Die GDI soll diese Abläufe verbessern, nicht einfach mehr Technik bereitstellen.** Geeignete gemeinsame Daten sollen an einer führenden Stelle gepflegt werden. Berechtigte Mitarbeitende können dieselbe freigegebene Informationsgrundlage in ihren Projekten verwenden. Für gelegentliche Anwender sind bei Bedarf einfache Webkarten vorgesehen; mobile Erfassungen gelangen erst nach fachlicher Prüfung in den führenden Bestand.

**Ziel der ersten Piloten:** Konkrete Verbesserungen in Baubetreuung und Verkehrsanlagenplanung umsetzen, nicht den grundsätzlichen Nutzen einer GDI neu beweisen. Die Managemententscheidung betrifft **Einführungsweg, Ressourcen und tragfähigen Betrieb**. Bisher liegen keine belastbaren Zeit- oder Kosteneinsparungszahlen vor. [Fachliche Begründung](01_PROJEKTKONZEPT.md#warum-wir-vic-gdi-einführen-wollen).

## Konkreter Mehrwert für VIC

- **Verlässliche Datengrundlage:** Geeignete Geodaten werden mit klarer Zuständigkeit gemeinsam geführt, statt unabhängig kopiert und unterschiedlich fortgeschrieben.
- **Effizientere Zusammenarbeit:** Berechtigte Projektteams greifen auf denselben Datenstand zu; unnötige Abstimmungs- und Übergabeschritte können reduziert werden.
- **Bessere Verfügbarkeit:** Wiederkehrende Datenquellen, Karten und GIS-Ressourcen sind einfacher auffindbar und für weitere Projekte nutzbar.
- **Zugänglichkeit für mehr Mitarbeitende:** Einfache Webkarten können Informationen auch ohne QGIS-Arbeitsplatz bereitstellen.
- **Kontrollierte mobile Abläufe:** Erfasste Informationen werden nachvollziehbar geprüft und übernommen; problematische synchronisierte GIS-Arbeitsablagen können ersetzt werden.
- **Zukunftsfähige Organisation:** Offene Schnittstellen, zentrale Ressourcen und dokumentierte Betriebswege erleichtern die Weiterentwicklung und mindern Abhängigkeiten von Einzelpersonen.

**Wichtig:** Das sind nachvollziehbare Ziele und strukturelle Vorteile der GDI, **keine bereits gemessenen Einsparbeträge**. Die Pilotbereiche setzen erste Verbesserungen um und liefern Erfahrungen zur Optimierung des weiteren Ausbaus.

## Aktueller Beschlussbedarf: Vorbereitung von A39

**A39 ist noch offen:** Die Geschäftsführung und IT sollen auf Grundlage realer Ressourcen **vier voneinander zu trennende Fragen** bewerten: Wer baut die GDI auf (intern, gemeinsam, extern)? Welches Wissen wird intern benötigt? Wer betreut die Systeme dauerhaft? **Wo und in welcher Form wird die GDI bereitgestellt – eigene Infrastruktur (H1), gemietete Server mit eigener GDI (H2), betreutes Hosting (H3) oder GDI as a Service (H4)?** Diese Fragen hängen zusammen, sind aber nicht mit einer einzigen Softwareentscheidung beantwortet. Vollständige Varianten: [A39-Grundlage](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md).

**Jetzt erbeten:** Fachliche Projektverantwortung, IT-Ansprechperson und Beteiligte der beiden Piloten benennen; begrenzte Zeit für Ist-Aufnahme, fachliche Pilotdefinition sowie GIS-/IT-Kompetenz- und Kapazitätsklärung priorisieren. Das ist **noch keine Freigabe für Aufbau, Beauftragung oder Produktivbetrieb**. Nach der Vorbereitung folgt die Entscheidung über Modell, Budget und Pilotumfang. Siehe [nächste Managemententscheidungen](#nächste-managemententscheidungen).

## Softwarelizenzen: zentraler Kostenvorteil

**Die geplante VIC-GDI setzt für ihren eigentlichen technischen Kern auf freie Open-Source-Software. Für die vorgesehenen Komponenten sind grundsätzlich keine zusätzlichen Softwarelizenzgebühren, Nutzerlizenzen oder verpflichtenden Hersteller-Abonnements erforderlich.** Das betrifft QGIS Desktop und QGIS Server, PostgreSQL/PostGIS sowie die zur Auswahl stehenden freien Webviewer (z. B. Lizmap/QWC2). Auch die bereits eingesetzte QField-App ist kostenlos. Die konkrete Komponentenauswahl und Lizenzprüfung erfolgt bei der Pilotplanung.

**Auch Proxmox VE kann gewerblich kostenlos betrieben werden.** Eine kostenpflichtige Proxmox-Subskription ist **nicht für die Nutzung vorgeschrieben**; sie kann für das Enterprise-Update-Repository und Herstellersupport aus betrieblichen Gründen sinnvoll sein. Ob bestehende IT-Subskriptionen und Serverkapazitäten ausreichen, klärt die IT.

**Keine Lizenzgebühren für den freien GDI-Kern bedeuten keinen kostenlosen Betrieb.** Aufbau, interne Arbeitszeit, Schulungen, Support, Backup, gegebenenfalls zusätzliche Hardware-/Proxmox-Kapazitäten, optionale QFieldCloud und externe Geodatenrechte sind separat zu bewerten. **H2/H3** verursachen Infrastruktur-/Managed-Entgelte, **H4** Plattformgebühren. Ob vorhandene Ressourcen für **H1** genügen oder zusätzliche CPU-, RAM-, Speicher- oder Backup-Kapazitäten benötigt werden, kann **nur die IT anhand der tatsächlichen Pilotlast** klären; weder Mehrbedarf noch Beschaffung sind bisher festgestellt. Softwarelizenzen und Quellen: [Übersicht](software/README.md#lizenz--und-kostenüberblick-gdi-kern). Vollständiger [Kostenrahmen](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md#kostenrahmen-und-lizenzabgrenzung).

## Erste Einführungsschritte und konkrete Ergebnisse

| Pilotbereich | Möglicher erster Einführungsablauf | Überprüfbares Umsetzungsergebnis |
|---|---|---|
| Baubetreuung | Bei der [Bestandsdokumentation (BB-01)](05_PILOTKONKRETISIERUNG.md#bb-01) einen vor Ort erfassten Leitungsverlauf prüfen und in einen führenden Bestand übernehmen. | Freigegebener Stand, Herkunft und Prüfstatus sind nachvollziehbar. Übergabeschritte und aufgetretene Datenkonflikte werden erfasst. |
| Verkehrsanlagenplanung | Einen wiederkehrenden Geodatenbestand aus zwei Planungsprojekten nutzen. | Beide Projekte finden den freigegebenen Stand mit den vorgesehenen Rechten. Suchaufwand und Zahl zusätzlicher Arbeitskopien werden mit dem heutigen Ablauf verglichen. |

Die Fachbereiche priorisieren je Pilot einen ersten Ablauf und definieren vor der Umsetzung nachvollziehbare Abnahmekriterien. Wo Aufwand oder Zeitgewinn beziffert werden sollen, werden geeignete Ausgangswerte erfasst. Beide Pilotbereiche können zeitlich gestaffelt eingeführt werden. Details und Status der Anwendungsfälle stehen in der [Pilotkonkretisierung](05_PILOTKONKRETISIERUNG.md).

## Investitions- und Ressourcenfelder

| Einmaliger Aufbau | Dauerhafter Aufwand |
|---|---|
| Bestandsaufnahme, Pilotkonzeption, Datenmigration | Datenpflege und Weiterentwicklung |
| Einrichtung von DB, Diensten und Anwendungen | Betrieb, Updates, Sicherheit, Backup |
| Technische [PoCs](ANHANG_A_GLOSSAR.md#poc), Tests, Einführung | Support und Fehlerbehebung |
| Wissensaufbau und Schulungen; ggf. externe Beratung/Umsetzung je nach Modell | Auffrischung, Dokumentationspflege, Vertretung; ggf. externer Spezialistensupport oder Betriebsvertrag |

**[Ressourcen für den Wissensaufbau](04_ENTSCHEIDUNGEN.md#a33):** Wissensaufbau benötigt explizit eingeplante personelle, zeitliche und gegebenenfalls finanzielle Ressourcen. Selbststudium ist nicht kostenfrei. Die Methode (Eigenlernen, gezielte Schulung, umfassende Qualifikation) richtet sich nach Rolle, Risiko und Wirtschaftlichkeit.

## Wer setzt die GDI um – und wer betreibt sie anschließend?

**A39 bleibt offen.** Zu vergleichen sind die Umsetzungswege A1–A3/B1/C1–C2, Wissensaufbau, Betrieb D1–D3 und Hosting H1–H4. **A3 oder B1 mit D2 und H1/H2** ist fachlich prüfenswert, sofern interne Kapazitäten und Vertretungen gesichert sind; H2 ersetzt keine Administration, H3/H4 können abhängig vom Vertrag weiter entlasten. **Das ist keine Vorentscheidung.** Maßgeblich sind QGIS-/PostGIS-Eignung, Datenhoheit, sichere Integration, Exit, interne Personentage und Gesamtkosten. [Variantenvergleich und Kriterien](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md).

## Organisationsmodell

GIS-Team verantwortet fachliche GDI-Fragen, IT die Infrastruktur und Basis-Sicherheit; Datenhoheit liegt bei den zuständigen Fachbereichen. Die konkrete [Betriebsverantwortung](04_ENTSCHEIDUNGEN.md#a31) für Datenbank und GIS-Dienste ist noch festzulegen. Kein neues umfangreiches Service-Management-System vorgesehen.

## Risiken und Gegenmaßnahmen

- **Überlastung des GIS-Teams:** priorisierter [MVP](ANHANG_A_GLOSSAR.md#mvp), klarer Supportprozess, realistische Kapazitäten.
- **Zu großer Funktionsumfang:** Standard vor Sonderentwicklung; Piloten statt Big Bang.
- **Datenkonflikte:** führende Datenbestände und kontrollierte Migration.
- **Unklare IT-Verantwortung:** frühe Abstimmung und Zuständigkeitsmatrix.
- **Fehlende Kompetenzen:** gezielte Qualifizierung und Vertretungsregelungen.

## Nächste Managemententscheidungen

**Erbetener Beschluss für die Vorbereitung:** Eine fachliche Projektverantwortung und je eine Ansprechperson aus IT und den beiden Pilotbereichen benennen. Zeit für Bestandsaufnahme, Pilotkonzeption, IT-Abstimmung und Einarbeitungsplanung einräumen und die Priorität gegenüber laufenden Projekten festlegen.

### Folgeentscheidung

Das Team legt priorisierte Abläufe, Erfolgskriterien, einmaligen Aufwand, laufenden Betriebsbedarf, Risiken sowie **realistische Varianten für Umsetzung, Wissensaufbau und späteren Betrieb** vor. Auf dieser Grundlage entscheidet die Geschäftsführung über Umfang, Budget und Start der Piloten; das **Organisations- und Betriebsmodell** wird mit der IT in den jeweiligen Zuständigkeiten festgelegt. Die IT bestätigt vorher den tragfähigen Betriebsrahmen.

**Gesprächsablauf (Vorschlag, 30 Minuten):** 5 Minuten Ausgangslage und Nutzen, 10 Minuten Piloten und Erfolgskriterien, 10 Minuten Ressourcen und Risiken, 5 Minuten Beschluss und Zuständigkeiten.

Weitere Details: [Projektkonzept](01_PROJEKTKONZEPT.md), [Roadmap](07_ROADMAP.md), [Entscheidungen](04_ENTSCHEIDUNGEN.md).
