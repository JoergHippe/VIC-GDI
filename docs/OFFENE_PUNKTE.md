# Offene Punkte und zurückgestellte Entscheidungen

**Status:** Interner Arbeitsentwurf · Stand 2026-11-03. Hier stehen Aufgaben zur Klärung, **keine vorweggenommenen Beschlüsse**.

## Architekturentscheidungen

| Bezug | Offene Frage | Nächster sinnvoller Schritt |
|---|---|---|
| A10 | QGIS Server: tatsächliche Eignung, benötigte OGC-Funktionen | Technischer PoC mit realer Pilotkarte |
| A12 | Objektselektion vs. geometrisches Clipping; Berechtigungen/Export | PoC mit typischen Layern, CRS und Formaten |
| A13 | QField/Happy Mini Q: Offline-Sync, Konflikte und Sicherheit | Reale mobile Pilotszenarien |
| A24 | Natives VM-Deployment vs. Hybrid vs. Container | IT-Workshop, Variantenvergleich; **noch keine Entscheidung** |
| A25 | IdP/SSO, Desktop-QGIS, externe Identitäten | Mit IT/Auth-Verantwortlichen konkretisieren |
| A26 | Rollen, Gruppen, Datenbank-/Dienstrechte | Rechte-Matrix und Zugriffstests über alle Schnittstellen |
| A27 | Technische Ausgestaltung TEST/PROD | IT-Abstimmung |
| A28 | Backupumfang, Restore, RPO/RTO, mobile Offline-Daten | IT-Abstimmung und Wiederherstellungstest |
| A29 | Funktionale GIS-Checks, Alarmierung und Log-Retention | Bestehendes IT-Monitoring aufnehmen |
| A30 | Git-Arbeitsweise, Deployment-Skripte, Freigabeverfahren | GIS/IT gemeinsam festlegen |
| A31 | Konkrete Aufgabenverteilung und Vertretungen | Schlanke Zuständigkeitsmatrix GIS/IT |
| A35 | Tatsächlicher MVP-Umfang und Abnahmekriterien | Pilot-Use-Cases priorisieren |
| A36 | Bestandsaufnahme und Migrationsplanung BB | Datenquellen, Dubletten, Konflikte und Pfade inventarisieren |
| A37 | Pflege und Lebenszyklus zentraler Daten | **Zurückgestellt**; Option B nur Empfehlung |
| A38 | PostGIS-Constraints, QGIS-Eingabevalidierung | **Zurückgestellt**; Option B nur Empfehlung |

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
