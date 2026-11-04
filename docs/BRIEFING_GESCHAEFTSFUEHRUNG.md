# Geschäftsführungs-Briefing – VIC-GDI

**Status:** Interner Arbeitsentwurf · Entscheidungsgrundlage, keine Kosten- oder Terminzusage.

## Zielbild

Eine gemeinsame [Geodateninfrastruktur](ANHANG_A_GLOSSAR.md#gdi) soll Geodaten fachbereichsübergreifend nutzbar machen, Mehrfachhaltung reduzieren und [GIS](ANHANG_A_GLOSSAR.md#gis)-Arbeitsabläufe in der Infrastrukturplanung zuverlässiger gestalten. Sie ergänzt die bestehenden [CAD](ANHANG_A_GLOSSAR.md#cad)-, [BIM](ANHANG_A_GLOSSAR.md#bim)-, M365- und Fachabläufe um eine gemeinsame Geodatenbasis. Die Einführung erfolgt schrittweise mit zwei Pilotbereichen: Baubetreuung/Bauüberwachung und Verkehrsanlagenplanung.

## Softwarelizenzen: zentraler Kostenvorteil

**Die geplante VIC-GDI setzt für ihren eigentlichen technischen Kern auf freie Open-Source-Software. Für die vorgesehenen Komponenten sind grundsätzlich keine zusätzlichen Softwarelizenzgebühren, Nutzerlizenzen oder verpflichtenden Hersteller-Abonnements erforderlich.** Das betrifft QGIS Desktop und QGIS Server, PostgreSQL/PostGIS sowie die zur Auswahl stehenden freien Webviewer (z. B. Lizmap/QWC2). Auch die bereits eingesetzte QField-App ist kostenlos. Die konkrete Komponentenauswahl und Lizenzprüfung erfolgt bei der Pilotplanung.

**Auch Proxmox VE kann gewerblich kostenlos betrieben werden.** Eine kostenpflichtige Proxmox-Subskription ist **nicht für die Nutzung vorgeschrieben**; sie kann für das Enterprise-Update-Repository und Herstellersupport aus betrieblichen Gründen sinnvoll sein. Ob bestehende IT-Subskriptionen und Serverkapazitäten ausreichen, klärt die IT.

**Keine Lizenzgebühren für die Kernsoftware ≠ keine Projektkosten.** Personal für Aufbau, Betrieb und Qualifizierung, Support sowie optionale Zusatzdienste (z. B. gehostete QFieldCloud-Synchronisation) müssen separat bewertet werden. **Auch eine Aufstockung vorhandener Hardware-Ressourcen kann erforderlich werden**, insbesondere von Speicherplatz, Arbeitsspeicher (RAM), CPU-Leistung oder Backup-Kapazität. **Ob und in welchem Umfang tatsächlich zusätzlicher Bedarf besteht und welche Kosten daraus entstehen, kann nur die IT nach Prüfung der vorhandenen Infrastruktur und des konkreten Pilotbedarfs beurteilen.** Ein zusätzlicher Hardwarebedarf ist derzeit weder festgestellt noch ausgeschlossen. Bestehende Unternehmenssoftware- und externe Geodatenlizenzen sind davon nicht automatisch abgedeckt. Eine Kosten- oder Budgetzusage lässt sich daraus nicht ableiten.

Nachweise und Abgrenzungen: [Softwarelizenzen und Kostenrahmen](ANHANG_C_SOFTWARE_LIZENZEN_KOSTEN.md).

## Erwarteter Nutzen – noch zu validieren

- Weniger redundante, widersprüchliche Geodatenstände.
- Verlässlicher Zugriff auf gemeinsame Projekt- und Fachdaten.
- Einfachere Karteninformationen auch für gelegentliche Anwender.
- Bessere Wiederverwendbarkeit von GIS-Diensten, Datenmodellen und Vorlagen.
- Weniger Probleme durch ungeeignete synchronisierte GIS-Arbeitsverzeichnisse.
- Verbesserte Nachvollziehbarkeit und geringere technische Abhängigkeiten von Einzelpersonen.

Dies sind **Zielwirkungen**, keine bereits gemessenen Einsparungen.

## Pilotvorschläge und Erfolgskriterien

| Pilot | Möglicher erster Ablauf | Späterer Nachweis |
|---|---|---|
| Baubetreuung/Bauüberwachung | Bei der [Bestandsdokumentation (BB-01)](05_PILOTKONKRETISIERUNG.md#bb-01) einen vor Ort erfassten Leitungsverlauf prüfen und in einen führenden Bestand übernehmen. | Freigegebener Stand, Herkunft und Prüfstatus sind nachvollziehbar. Übergabeschritte und aufgetretene Datenkonflikte werden erfasst. |
| Verkehrsanlagenplanung | Einen wiederkehrenden Geodatenbestand aus zwei Planungsprojekten nutzen. | Beide Projekte finden den freigegebenen Stand mit den vorgesehenen Rechten. Suchaufwand und Zahl zusätzlicher Arbeitskopien werden mit dem heutigen Ablauf verglichen. |

Die Fachbereiche priorisieren je Pilot einen ersten Ablauf und legen vor der Umsetzung Ausgangswerte und Abnahmekriterien fest. Beide Piloten können zeitlich gestaffelt werden. Details und Status der Anwendungsfälle stehen in der [Pilotkonkretisierung](05_PILOTKONKRETISIERUNG.md).

## Investitions- und Ressourcenfelder

| Einmaliger Aufbau | Dauerhafter Aufwand |
|---|---|
| Bestandsaufnahme, Pilotkonzeption, Datenmigration | Datenpflege und Weiterentwicklung |
| Einrichtung von DB, Diensten und Anwendungen | Betrieb, Updates, Sicherheit, Backup |
| Technische [PoCs](ANHANG_A_GLOSSAR.md#poc), Tests, Einführung | Support und Fehlerbehebung |
| Wissensaufbau und Schulungen; ggf. externe Beratung/Umsetzung je nach Modell | Auffrischung, Dokumentationspflege, Vertretung; ggf. externer Spezialistensupport oder Betriebsvertrag |

**[Ressourcen für den Wissensaufbau](04_ENTSCHEIDUNGEN.md#a33):** Wissensaufbau benötigt explizit eingeplante personelle, zeitliche und gegebenenfalls finanzielle Ressourcen. Selbststudium ist nicht kostenfrei. Die Methode (Eigenlernen, gezielte Schulung, umfassende Qualifikation) richtet sich nach Rolle, Risiko und Wirtschaftlichkeit.

## Wer setzt die GDI um – und wer betreibt sie anschließend?

**Noch keine Entscheidung:** Die [Umsetzungs- und Betriebsmodelle](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md) stellen alle derzeit sinnvollen Möglichkeiten gegenüber: **A1–A3** (interner Aufbau mit Selbststudium, Schulungen oder zusätzlich Beratung), **B1** (gemeinsame Implementierung mit externen Spezialisten) sowie **C1/C2** (externe Umsetzung mit Übergabe bzw. einschließlich Betrieb). Der **Wissensaufbau** und der spätere **Betrieb D1–D3** (intern, intern mit Spezialistensupport, überwiegend extern) sind dabei **eigenständige Entscheidungen**; Mischmodelle je Komponente sind zulässig.

**Vorläufig fachlich prüfenswert** ist A3 oder B1 mit D2, **sofern** GIS-Team und IT ausreichend Zeit, Kompetenzen und Vertretung bereitstellen können. Das ist **keine Vorentscheidung**; bei fehlender interner Kapazität können externe Gesamtleistungen sinnvoller sein. Bei allen Varianten zählen **interne Personentage, Schulungen, externe Leistungen, Betriebskosten und Wissenstransfer**, nicht nur externe Rechnungen. Auch Fremdbetrieb setzt internes Steuerungswissen voraus.

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
