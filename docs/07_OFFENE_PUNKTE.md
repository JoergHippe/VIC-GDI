# Offene Punkte und zurückgestellte Entscheidungen

**Status:** Interner Arbeitsentwurf. Hier stehen Aufgaben zur Klärung, **keine vorweggenommenen Beschlüsse**.

Gesprächsunterlagen: [IT-Briefing](BRIEFING_IT.md) und [Geschäftsführungs-Briefing](BRIEFING_GESCHAEFTSFUEHRUNG.md). Die [Prüfaufträge zu A04, A15 und A36](04_ENTSCHEIDUNGEN.md#erneute-prüfung-a04-a15-und-a36) ergänzen die bisherigen Beschlüsse. Die nächsten Termine dienen der Planung und Abstimmung. Praktische Erprobungen folgen bei Bedarf nach gesonderter Freigabe.

## Architekturentscheidungen

| Bezug | Offene Frage | Nächster sinnvoller Schritt |
|---|---|---|
| A10 | [QGIS](ANHANG_A_GLOSSAR.md#qgis) Server: tatsächliche Eignung, benötigte OGC-Funktionen | Bei priorisiertem Webbedarf technischer [PoC](ANHANG_A_GLOSSAR.md#poc) mit repräsentativer Pilotkarte |
| A12 | Objektselektion vs. geometrisches Clipping; Berechtigungen/Export | PoC mit typischen Layern, CRS und Formaten |
| A13 | QField/Happy Mini Q: Offline-Sync, Konflikte und Sicherheit | Reale mobile Pilotszenarien |
| A24 | Natives VM-Deployment vs. Hybrid vs. Container | IT-Workshop, Variantenvergleich; **noch keine Entscheidung** |
| A25 | IdP/SSO, Desktop-QGIS, externe Identitäten | Mit IT/Auth-Verantwortlichen konkretisieren |
| A26 | Rollen, Gruppen, Datenbank-/Dienstrechte | Rechte-Matrix und Zugriffstests über alle Schnittstellen |
| A27 | Technische Ausgestaltung TEST/PROD | IT-Abstimmung |
| A28 | Backupumfang, Restore, RPO/RTO, mobile Offline-Daten | IT-Abstimmung und Wiederherstellungstest |
| A29 | Funktionale GIS-Checks, Alarmierung und Log-Retention | Bestehendes IT-Monitoring aufnehmen |
| A30 | [Git](ANHANG_A_GLOSSAR.md#git)-Arbeitsweise, Deployment-Skripte, Freigabeverfahren | GIS/IT gemeinsam festlegen |
| A31 | Konkrete Aufgabenverteilung und Vertretungen | Schlanke Zuständigkeitsmatrix GIS/IT |
| A35 | Tatsächlicher [MVP](ANHANG_A_GLOSSAR.md#mvp)-Umfang und Abnahmekriterien | Pilot-Use-Cases priorisieren |
| A04/A36 | Zentrale PostgreSQL-Projektablage und Auswirkungen auf Migration | GIS und IT grenzen geeignete Projekte anhand des Inventars ein. Der [Prüfrahmen](04_ENTSCHEIDUNGEN.md#prüfrahmen-für-die-projektablage-a04a36) dient der späteren Erprobung. |
| A15 | Erweiterter interner Katalog und hybride Metadatenpflege | GIS und Fachbereiche priorisieren Suchfälle und Felder. Mit IT automatisierbare Quellen und mit den Fachbereichen redaktionelle Zuständigkeiten abgrenzen. |
| A36 | Bestandsaufnahme und Migrationsplanung BB | Datenquellen, Dubletten, Konflikte und Pfade inventarisieren. |
| A37 | Pflege und Lebenszyklus zentraler Daten | **Zurückgestellt**; Option B nur Empfehlung |
| A38 | [PostGIS](ANHANG_A_GLOSSAR.md#postgis)-Constraints, QGIS-Eingabevalidierung | **Zurückgestellt**; Option B nur Empfehlung |

Für die beiden Pilotbereiche liegt ein [Erhebungsleitfaden](05_PILOTKONKRETISIERUNG.md) vor. Die Baubetreuung hat Tätigkeiten benannt und nutzt bereits mobile Werkzeuge. Für beide Piloten stehen die Auswahl des ersten Ablaufs und seine Abnahmekriterien aus.

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
- Für die von IT betreibbaren Varianten die offenen Aufwandsannahmen zu Einrichtung, Betrieb und Qualifizierung ergänzen.
- Beschlossene Architektur und technische Vorzugsvarianten stets unterscheiden.

Bei der Pilotkonkretisierung Datenschutz, Lizenzbedingungen und interne Sicherheitsvorgaben für die tatsächlich genutzten Daten und Zugriffspfade klären. Standards dienen als fachliche Orientierung.
