# Offene Punkte und zurückgestellte Entscheidungen

**Status:** Interner Arbeitsentwurf · Stand 2026-11-03. Hier stehen Aufgaben zur Klärung, **keine vorweggenommenen Beschlüsse**.

Gesprächsunterlagen: [IT-Briefing](BETRIEB_UND_IT.md) und [Geschäftsführungs-Briefing](MANAGEMENT.md). Die [Prüfaufträge zu A04, A15 und A36](ENTSCHEIDUNGEN.md#erneute-prüfung-a04-a15-und-a36) ergänzen die bisherigen Beschlüsse. Die nächsten Termine dienen der Planung und Abstimmung.

## Architekturentscheidungen

| Bezug | Offene Frage | Nächster sinnvoller Schritt |
|---|---|---|
| A10 | [QGIS](GLOSSAR.md#qgis) Server: tatsächliche Eignung, benötigte OGC-Funktionen | Technischer [PoC](GLOSSAR.md#poc) mit realer Pilotkarte |
| A12 | Objektselektion vs. geometrisches Clipping; Berechtigungen/Export | PoC mit typischen Layern, CRS und Formaten |
| A13 | QField/Happy Mini Q: Offline-Sync, Konflikte und Sicherheit | Reale mobile Pilotszenarien |
| A24 | Natives VM-Deployment vs. Hybrid vs. Container | IT-Workshop, Variantenvergleich; **noch keine Entscheidung** |
| A25 | IdP/SSO, Desktop-QGIS, externe Identitäten | Mit IT/Auth-Verantwortlichen konkretisieren |
| A26 | Rollen, Gruppen, Datenbank-/Dienstrechte | Rechte-Matrix und Zugriffstests über alle Schnittstellen |
| A27 | Technische Ausgestaltung TEST/PROD | IT-Abstimmung |
| A28 | Backupumfang, Restore, RPO/RTO, mobile Offline-Daten | IT-Abstimmung und Wiederherstellungstest |
| A29 | Funktionale GIS-Checks, Alarmierung und Log-Retention | Bestehendes IT-Monitoring aufnehmen |
| A30 | [Git](GLOSSAR.md#git)-Arbeitsweise, Deployment-Skripte, Freigabeverfahren | GIS/IT gemeinsam festlegen |
| A31 | Konkrete Aufgabenverteilung und Vertretungen | Schlanke Zuständigkeitsmatrix GIS/IT |
| A35 | Tatsächlicher [MVP](GLOSSAR.md#mvp)-Umfang und Abnahmekriterien | Pilot-Use-Cases priorisieren |
| A04/A36 | Zentrale PostgreSQL-Projektablage und Auswirkungen auf Migration | GIS und IT vergleichen Projektablage, Berechtigungen, Publikation und Wiederherstellung auf Basis des Projektinventars. |
| A15 | Erweiterter interner Katalog und hybride Metadatenpflege | GIS und Fachbereiche priorisieren Suchfälle und Felder. Mit IT automatisierbare Quellen und mit den Fachbereichen redaktionelle Zuständigkeiten abgrenzen. |
| A36 | Bestandsaufnahme und Migrationsplanung BB | Datenquellen, Dubletten, Konflikte und Pfade inventarisieren. |
| A37 | Pflege und Lebenszyklus zentraler Daten | **Zurückgestellt**; Option B nur Empfehlung |
| A38 | [PostGIS](GLOSSAR.md#postgis)-Constraints, QGIS-Eingabevalidierung | **Zurückgestellt**; Option B nur Empfehlung |

Für die beiden Pilotbereiche liegt ein [Erhebungsleitfaden](PILOTKONKRETISIERUNG.md) vor. Die dort aufgeführten Anwendungsfälle sind noch nicht fachlich bestätigt.

## Fachliche Konkretisierung

- Pilot-Use-Cases mit echten Anwendern und Erfolgskriterien aufnehmen.
- Gemeinsame Datenbestände, fachliche Datenhoheit und Ausnahmen ermitteln.
- Projektstammdaten, optionale Geometrie und Projektbezug praktisch prüfen.
- Datenkatalog-Felder und Lizenzrestriktionen mit realen Daten testen.
- Zielgruppen für einfache Webkartenansichten und mobile Bedienung festlegen.
- Abgrenzung zwischen gemeinsamem GDI-Kern und Fachbereichserweiterungen schärfen.

## Dokumentationsqualität

- A01–A38 anhand der ursprünglichen Gesprächsprotokolle bei Verfügbarkeit einzeln gegenprüfen; die Erstfassung ist eine konsolidierte Zusammenfassung, keine vollständige Transkription.
- Anforderungen mit überprüfbaren Akzeptanzkriterien ergänzen, wenn die jeweiligen Piloten konkret werden.
- Varianten- und Wirtschaftlichkeitsvergleich A24 ausführlich für IT dokumentieren, sobald die Abstimmung vorbereitet wird.
- Beschlossene Architektur und technische Vorzugsvarianten stets unterscheiden.

## Systemweiter Architektur- und Konsistenzreview (2026-11-03)

**Umfang:** Dokumentierte Grundsätze A01–A38 und die initialen Dokumente. **Ergebnis:** Keine offensichtlichen inhaltlichen Grundsatzwidersprüche, aber wesentliche Konkretisierungs- und Validierungslücken. Dies ist ein Dokumentationsreview, keine technische Abnahme.

1. **Entscheidungsstatus:** A24 offen; A37 und A38 zurückgestellt. IT-nahe Entscheidungen enthalten teils nur die bevorzugte Richtung, keine technische Freigabe. Diese Unterscheidung ist beizubehalten.
2. **Datenhaltung:** A02 und A36 sind vereinbar: Gemeinsame geeignete Vektordaten zentral in PostGIS, andere geeignete Fachdateien auf Fileservern. Keine pauschale Migration aller Daten in eine Datenbank.
3. **Zugriff und Datenhoheit:** A08/A09/A26 sind konzeptionell konsistent; eine konkrete Rechte-Matrix und End-to-End-Prüfungen über Datenbank, GIS-Dienste, Web, Export und Mobil fehlen noch.
4. **Pilot und MVP:** A34/A35 sind konsistent, aber konkrete Anwendungsfälle, überprüfbare Abnahmekriterien und Kapazitätsannahmen fehlen. Keine Termin- oder Kostenzusagen ohne belastbare Grundlage.
5. **IT-Betrieb:** A23–A31 benötigen eine gemeinsame IT-Abstimmung zu Deployment, Authentifizierung, Zuständigkeiten, Backup/Restore und Monitoring. Keine voreilige Festlegung auf Container oder native VMs.
6. **Technologievalidierung:** QGIS Server, Webviewer, Extract und mobile Synchronisation anhand echter Pilotfälle erproben. Zukunftsfähigkeit und Wartungsaufwand ausdrücklich bewerten.
7. **Normen und Compliance:** Standards als Orientierung verwenden; konkrete Datenschutz-, Lizenz- und Sicherheitsanforderungen gesondert prüfen. Keine pauschale ISO-/INSPIRE-Konformität behaupten.
8. **Dokumentationsqualität:** Führende Stellen sind definiert; Glossar ergänzt. Bei Beschlussänderungen alle betroffenen Sichten gemeinsam aktualisieren. Originalgespräche A01–A38 bei Verfügbarkeit gegenprüfen, da die Erstkonsolidierung auf Gesprächszusammenfassungen beruht.

**Priorität:** Pilot-Anwendungsfälle und IT-Abstimmung zuerst, technische PoCs danach. A37/A38 bleiben zurückgestellt. Keine zusätzliche Governance- oder Toolplattform allein aus diesem Review ableiten.
