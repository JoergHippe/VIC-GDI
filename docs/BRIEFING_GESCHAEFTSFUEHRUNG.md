# Geschäftsführungs-Briefing – VIC-GDI

**Status:** Interner Arbeitsentwurf · Entscheidungsgrundlage, keine Kosten- oder Terminzusage.

## Zielbild

**GIS-Team und beteiligte Fachkollegen möchten VIC-GDI als unternehmensweite, fachbereichsneutrale [Geodateninfrastruktur](ANHANG_A_GLOSSAR.md#gdi) etablieren.** Sie soll gemeinsame Datenbestände zuverlässiger nutzbar machen, Mehrfachpflege reduzieren und [GIS](ANHANG_A_GLOSSAR.md#gis)-Arbeitsabläufe in der VIC vereinfachen. Die vorhandenen [CAD](ANHANG_A_GLOSSAR.md#cad)-, [BIM](ANHANG_A_GLOSSAR.md#bim)- und Fachsysteme werden ergänzt, nicht ersetzt. **Vorgeschlagen wird eine gestaffelte Einführung**, beginnend in Baubetreuung und Verkehrsanlagenplanung. Für Umsetzung, Ressourcen und Betrieb sind die Entscheidungen von Geschäftsführung und IT noch erforderlich.

## Warum das Vorhaben wichtig ist

Heute verteilen sich Geodaten und QGIS-Projekte auf unterschiedliche Speicherorte und fachliche Zuständigkeiten. Für vergleichbare Aufgaben werden teils Daten kopiert und projektweise weiterbearbeitet. Das kann die Suche nach dem richtigen Stand, die Abstimmung zwischen Beteiligten und die Weitergabe von Informationen erschweren. In der Baubetreuung ist außerdem die Nutzung synchronisierter Ordner für führende GIS-Arbeitsdaten ein konkreter Verbesserungsansatz.

**Die GDI soll diese Abläufe verbessern, nicht einfach mehr Technik bereitstellen.** Geeignete gemeinsame Daten sollen an einer führenden Stelle gepflegt werden. Berechtigte Mitarbeitende können dieselbe freigegebene Informationsgrundlage in ihren Projekten verwenden. Für gelegentliche Anwender sind bei Bedarf einfache Webkarten vorgesehen; mobile Erfassungen gelangen erst nach fachlicher Prüfung in den führenden Bestand.

**Zwei praktische Beispiele:** Die **Baubetreuung** kann vor Ort erfasste Leitungsverläufe kontrolliert übernehmen, statt mobile Arbeitsstände ungeprüft mit dem zentralen Bestand gleichzusetzen. In der **Verkehrsanlagenplanung** können mehrere Projekte geeignete gemeinsame Geodaten nutzen, ohne voneinander unabhängige Kopien fortzuschreiben.

**Die fachliche Begründung ist klar:** Gemeinsame, verantwortete Geodaten und standardisierte Zugriffswege verbessern die Voraussetzungen für Datenqualität, Zusammenarbeit und Wiederverwendung. Die anstehende Managemententscheidung betrifft den **geeigneten Einführungsweg, Prioritäten, Ressourcen und einen wirtschaftlich tragfähigen Betrieb**. Belastbare Zahlen zu eingesparter Arbeitszeit oder Geld liegen derzeit nicht vor und werden nicht unterstellt. Vertiefung: [Projektkonzept](01_PROJEKTKONZEPT.md#warum-wir-vic-gdi-einführen-wollen).

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

**Gemietete Server (H2/H3) und eine GDIaaS-Plattform (H4) verursachen laufende Miet-, Betriebs- beziehungsweise Serviceentgelte**, auch wenn Open-Source-Kernsoftware eingesetzt wird. Keine Lizenzgebühren für die Kernsoftware ≠ keine Projektkosten. Personal für Aufbau, Betrieb und Qualifizierung, Support sowie optionale Zusatzdienste (z. B. gehostete QFieldCloud-Synchronisation) müssen separat bewertet werden. **Für H1 kann eine Aufstockung vorhandener Hardware-Ressourcen erforderlich werden** (Speicherplatz, RAM, CPU oder Backup-Kapazität); bei H2/H3/H4 fallen an ihrer Stelle gegebenenfalls zusätzliche Miet-, Datenübertragungs- und Betriebsentgelte an. **Ob und in welchem Umfang tatsächlich zusätzlicher Bedarf besteht und welche Kosten daraus entstehen, kann nur die IT nach Prüfung der vorhandenen Infrastruktur und des konkreten Pilotbedarfs beurteilen.** Ein zusätzlicher Hardwarebedarf ist derzeit weder festgestellt noch ausgeschlossen. Bestehende Unternehmenssoftware- und externe Geodatenlizenzen sind davon nicht automatisch abgedeckt. Eine Kosten- oder Budgetzusage lässt sich daraus nicht ableiten.

Softwarelizenzen und Quellen: [Softwareübersicht](software/README.md#lizenz--und-kostenüberblick-gdi-kern). Einmalige und laufende Kosten: [Kostenrahmen der A39-Entscheidungsgrundlage](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md#kostenrahmen-und-lizenzabgrenzung).

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

**Noch keine Entscheidung:** Der [A39-Modellvergleich](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md) trennt **Umsetzung A1–A3/B1/C1–C2**, **Wissensaufbau**, **Betrieb D1–D3** und **Hosting/Bezug H1–H4**. Dadurch kann eine eigene GDI beispielsweise **auf vorhandenen VIC-Servern oder auf gemieteten Servern** aufgebaut und intern, unterstützt oder extern betreut werden. H4 ist dagegen eine fertige, extern betriebene GDI-Plattform als Dienstleistung. Es gibt **keine** Entscheidung für einen Anbieter oder ein Betriebsmodell.

**Vorläufig fachlich prüfenswert** ist A3 oder B1 mit D2 und H1 **oder H2**, sofern GIS-Team und IT ausreichend Zeit, Kompetenzen und Vertretung bereitstellen können. Die vorhandene Proxmox-Infrastruktur ist bei H1 zu berücksichtigen; **H2 spart eigene Serveranschaffung, nicht automatisch Betriebspersonal**. H3/H4 können je nach Fachfunktionen und Serviceangebot stärker entlasten. Das ist **keine Vorentscheidung**; entscheidend bleiben QGIS-/PostGIS-Integration, Datenhoheit, Portabilität und Gesamtkosten. Bei allen Varianten zählen **interne Personentage, Schulungen, externe Leistungen, Betriebskosten und Wissenstransfer**, nicht nur externe Rechnungen. Auch Fremdbetrieb setzt internes Steuerungswissen voraus.

**Offene Organisationsentscheidung ([A39](04_ENTSCHEIDUNGEN.md#a39)) durch Geschäftsführung und IT:** Nach Bestandsaufnahme und IT-Bewertung über Organisationsmodell, personelle Ressourcen, Budget/Beauftragung und tragfähigen Betriebsrahmen entscheiden; GIS-Team und Fachbereiche fachlich beteiligen. Detailvergleich, Vor-/Nachteile und Mindestanforderungen an externe Übergaben: [Gesonderte Entscheidungsgrundlage](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md).

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
