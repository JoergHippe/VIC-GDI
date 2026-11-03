# Geschäftsführungs-Briefing – VIC-GDI

**Status:** Interner Arbeitsentwurf · Entscheidungsgrundlage, keine Kosten- oder Terminzusage.

## Zielbild

Eine gemeinsame [Geodateninfrastruktur](ANHANG_A_GLOSSAR.md#gdi) soll Geodaten fachbereichsübergreifend nutzbar machen, Mehrfachhaltung reduzieren und [GIS](ANHANG_A_GLOSSAR.md#gis)-Arbeitsabläufe in der Infrastrukturplanung zuverlässiger gestalten. Sie ergänzt die bestehenden CAD-, BIM-, M365- und Fachabläufe um eine gemeinsame Geodatenbasis. Die Einführung erfolgt schrittweise mit zwei Pilotbereichen: Baubetreuung/Bauüberwachung und Verkehrsanlagenplanung.

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
| Wissensaufbau und Schulungen | Auffrischung, Dokumentationspflege, Vertretung |

**[Ressourcen für den Wissensaufbau](04_ENTSCHEIDUNGEN.md#a33):** Wissensaufbau benötigt explizit eingeplante personelle, zeitliche und gegebenenfalls finanzielle Ressourcen. Selbststudium ist nicht kostenfrei. Die Methode (Eigenlernen, gezielte Schulung, umfassende Qualifikation) richtet sich nach Rolle, Risiko und Wirtschaftlichkeit.

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

Das Team legt priorisierte Abläufe, Erfolgskriterien, einmaligen Aufwand, laufenden Betriebsbedarf und Risiken vor. Auf dieser Grundlage entscheidet die Geschäftsführung über Umfang, Budget und Start der Piloten. Die IT bestätigt vorher den tragfähigen Betriebsrahmen.

**Gesprächsablauf (Vorschlag, 30 Minuten):** 5 Minuten Ausgangslage und Nutzen, 10 Minuten Piloten und Erfolgskriterien, 10 Minuten Ressourcen und Risiken, 5 Minuten Beschluss und Zuständigkeiten.

Weitere Details: [Projektkonzept](01_PROJEKTKONZEPT.md), [Roadmap](06_ROADMAP.md), [Entscheidungen](04_ENTSCHEIDUNGEN.md).
