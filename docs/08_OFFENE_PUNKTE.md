# Offene Punkte und zurückgestellte Entscheidungen

**Status:** Interner Arbeitsentwurf. Hier stehen Aufgaben zur Klärung, **keine vorweggenommenen Beschlüsse**.

Gesprächsunterlagen: [IT-Briefing](BRIEFING_IT.md) und [Geschäftsführungs-Briefing](BRIEFING_GESCHAEFTSFUEHRUNG.md). Die [Prüfaufträge](04_ENTSCHEIDUNGEN.md#erneute-prüfung-a04-a15-und-a36) zu [A04](04_ENTSCHEIDUNGEN.md#a04), [A15](04_ENTSCHEIDUNGEN.md#a15) und [A36](04_ENTSCHEIDUNGEN.md#a36) ergänzen die bisherigen Beschlüsse. Die nächsten Termine dienen der Planung und Abstimmung. Praktische Erprobungen folgen bei Bedarf nach gesonderter Freigabe.

## Architekturentscheidungen

| Bezug | Offene Frage | Nächster sinnvoller Schritt |
|---|---|---|
| [A10](04_ENTSCHEIDUNGEN.md#a10) | [QGIS](ANHANG_A_GLOSSAR.md#qgis) Server: tatsächliche Eignung, benötigte [OGC](ANHANG_A_GLOSSAR.md#ogc)-Funktionen | Bei priorisiertem Webbedarf technischer [PoC](ANHANG_A_GLOSSAR.md#poc) mit repräsentativer Pilotkarte |
| [A12](04_ENTSCHEIDUNGEN.md#a12) | **Auswahl/Clipping und Formate/CRS fachlich entschieden:** Umsetzung und Validierung (GPKG, GeoJSON klassisch/RFC 7946 optional, DXF, CSV; Shapefile optional; EPSG:25832/25833/3068) noch offen. **Berechtigungsmodell ausdrücklich offen (Punkt 3, D).** | GIS/Fachbereiche/IT erheben Rollen, Datenbestände, Zugriffspfade; danach Positiv-/Negativtests, Objektselektion/Clipping, GeoJSON-CRS, CAD/DXF und Soldner-Transformationen im PoC prüfen; keine ungeschützten Exporte |
| [A13](04_ENTSCHEIDUNGEN.md#a13) | Mobiler Datenaustausch mit [QField](ANHANG_A_GLOSSAR.md#qfield): Offline-Sync, Konflikte und Sicherheit | [Cloud und lokalen USB-Transfer vergleichen](05_PILOTKONKRETISIERUNG.md#mobile-erfassung-und-datenaustausch). |
| [A24](04_ENTSCHEIDUNGEN.md#a24) | Natives [VM](ANHANG_A_GLOSSAR.md#vm)-Deployment vs. Hybrid vs. Container | IT-Workshop, Variantenvergleich; **noch keine Entscheidung** |
| [A25](04_ENTSCHEIDUNGEN.md#a25) | [IdP](ANHANG_A_GLOSSAR.md#idp)/[SSO](ANHANG_A_GLOSSAR.md#sso), Desktop-QGIS, externe Identitäten | Mit IT/Auth-Verantwortlichen konkretisieren |
| [A26](04_ENTSCHEIDUNGEN.md#a26) | Rollen, Gruppen, Datenbank-/Dienstrechte **einschließlich Exportwegen**; Granularität erst aus realen Datenbeständen und Nutzern ableiten | GIS/Fachbereiche/IT inventarisieren reale Zugriffswege (QGIS/PostGIS/Webdienst/Export), prüfen räumliche Begrenzungen, Views/Spalten und Download-/Zwischendateien; daraus Rechte-Matrix und Positiv-/Negativtests ableiten |
| [A27](04_ENTSCHEIDUNGEN.md#a27) | Technische Ausgestaltung TEST/PROD | IT-Abstimmung |
| [A28](04_ENTSCHEIDUNGEN.md#a28) | Backupumfang, Restore, [RPO/RTO](ANHANG_A_GLOSSAR.md#rpo-rto), mobile Offline-Daten | IT-Abstimmung und Wiederherstellungstest |
| [A29](04_ENTSCHEIDUNGEN.md#a29) | Funktionale [GIS](ANHANG_A_GLOSSAR.md#gis)-Checks, Alarmierung und Log-Retention | Bestehendes IT-Monitoring aufnehmen |
| [A30](04_ENTSCHEIDUNGEN.md#a30) | [Git](ANHANG_A_GLOSSAR.md#git)-Arbeitsweise, Deployment-Skripte, Freigabeverfahren | GIS/IT gemeinsam festlegen |
| [A31](04_ENTSCHEIDUNGEN.md#a31) | Konkrete Aufgabenverteilung und Vertretungen | Schlanke Zuständigkeitsmatrix GIS/IT |
| [A35](04_ENTSCHEIDUNGEN.md#a35) | Tatsächlicher [MVP](ANHANG_A_GLOSSAR.md#mvp)-Umfang und Abnahmekriterien | Pilot-Use-Cases priorisieren |
| [A04](04_ENTSCHEIDUNGEN.md#a04)/[A36](04_ENTSCHEIDUNGEN.md#a36) | Zentrale [PostgreSQL](ANHANG_A_GLOSSAR.md#postgresql)-Projektablage und Auswirkungen auf Migration | GIS und IT grenzen geeignete Projekte anhand des Inventars ein. Der [Prüfrahmen](04_ENTSCHEIDUNGEN.md#prüfrahmen-für-die-projektablage-a04a36) dient der späteren Erprobung. |
| [A15](04_ENTSCHEIDUNGEN.md#a15) | Erweiterter interner Katalog und hybride Metadatenpflege | GIS und Fachbereiche priorisieren Suchfälle und Felder. Mit IT automatisierbare Quellen und mit den Fachbereichen redaktionelle Zuständigkeiten abgrenzen. |
| [A36](04_ENTSCHEIDUNGEN.md#a36) | Bestandsaufnahme und Migrationsplanung BB | Datenquellen, Dubletten, Konflikte und Pfade inventarisieren. |
| [A37](04_ENTSCHEIDUNGEN.md#a37) | Pflege und Lebenszyklus zentraler Daten | **Zurückgestellt**; Option B nur Empfehlung |
| [A38](04_ENTSCHEIDUNGEN.md#a38) | [PostGIS](ANHANG_A_GLOSSAR.md#postgis)-Constraints, QGIS-Eingabevalidierung | **Zurückgestellt**; Option B nur Empfehlung |

Für die beiden Pilotbereiche liegt ein [Erhebungsleitfaden](05_PILOTKONKRETISIERUNG.md) vor. Die Baubetreuung hat Tätigkeiten benannt und nutzt bereits mobile Werkzeuge. Für beide Piloten stehen die Auswahl des ersten Ablaufs und seine Abnahmekriterien aus.

## Offene Organisationsentscheidung: Umsetzung und Betrieb

- **Wer setzt die GDI um? ([A39](04_ENTSCHEIDUNGEN.md#a39))** Die Optionen **A1–A3** (intern mit Selbststudium/Schulung/Beratung), **B1** (gemeinsame Umsetzung) und **C1/C2** (externe Umsetzung mit Übergabe bzw. Betrieb) sind in [06_UMSETZUNGS_UND_BETRIEBSMODELLE.md](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md) beschrieben und **nicht entschieden**.
- **Wie werden Wissen und dauerhafter Betrieb sichergestellt?** Schulungs-/Wissenstransferbedarf und **D1–D3** (interner, unterstützter oder überwiegend externer Betrieb) getrennt vom Aufbau klären ([A31](04_ENTSCHEIDUNGEN.md#a31), [A33](04_ENTSCHEIDUNGEN.md#a33)).
- **Nächster Schritt:** GIS/IT konkretisieren Kompetenzen, Personentage, Betriebsverantwortung, externe Leistungspakete und Gesamtkosten; **GF und IT wählen das Modell erst auf dieser Grundlage** in ihren jeweiligen Zuständigkeiten. A3/B1 mit D2 bleibt eine unverbindliche Prüfrichtung.

## Öffentliches GitHub-Repository: Freigabe- und Lizenzklärung

- Verifizieren, dass Konzeptinhalte und interne organisatorische Angaben für eine **öffentliche Veröffentlichung freigegeben** sind; bei Vertraulichkeitsbedenken umgehend mit den Verantwortlichen klären.
- Prüfen, ob und unter welchen Bedingungen Dritte die Dokumentation weiterverwenden dürfen. Eine fehlende `LICENSE`-Datei ist **keine** automatische Open-Source-Freigabe. Entscheidung durch die hierfür zuständigen Unternehmensstellen, nicht aus der GDI-Konzeption ableiten.
- Vorlagen, Bilder, Fremdtexte und andere Drittinhalte vor späterer Erweiterung auf Weitergaberechte prüfen; auch Git-Historie bei versehentlich veröffentlichten sensiblen Inhalten berücksichtigen.

## Kosten- und Lizenzklärung mit IT

- Den [Software-/Lizenzüberblick](software/README.md#lizenz--und-kostenüberblick-gdi-kern) und den [A39-Kostenrahmen](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md#kostenrahmen-und-lizenzabgrenzung) für den später ausgewählten GDI-MVP bestätigen: Kernsoftware, konkret eingesetzte Versionen/Erweiterungen und Open-Source-Lizenzpflichten.
- **Proxmox:** Bestehende Hosts und belegte CPU-Sockel, Subskriptions-/Repository-Strategie, Kapazitäten, Sicherung und mögliche Zusatzkosten mit IT klären; kostenpflichtige Subskription nicht als zwingende Softwarelizenz darstellen.
- **Hardware-Ressourcen (IT-Prüfauftrag):** Die IT beurteilt auf Basis der vorhandenen Infrastruktur und der konkretisierten Pilotlast, ob zusätzliche Kapazitäten für Speicherplatz, RAM, CPU und Backups oder neue Hardware nötig werden. Erst danach ggf. Kosten beziffern; noch keine Notwendigkeit oder Beschaffung unterstellen.
- Bei mobilem Datenaustausch optionalen Bedarf und mögliche Kosten einer gehosteten QFieldCloud von der kostenfreien QField-App trennen; erst nach Vergleich der Übertragungswege.
- Budgetschätzung nach Lizenzgebühren, einmaligen internen Aufwänden, laufendem Betrieb und optionalen Leistungen aufgliedern; keine pauschalen Einsparungen ohne Daten behaupten.

## Fachliche Konkretisierung

- Pilot-Use-Cases mit echten Anwendern und Erfolgskriterien aufnehmen.
- Gemeinsame Datenbestände, fachliche Datenhoheit und Ausnahmen ermitteln.
- Projektstammdaten, optionale Geometrie und Projektbezug praktisch prüfen.
- Datenkatalog-Felder und Lizenzrestriktionen mit realen Daten testen.
- Zielgruppen für einfache Webkartenansichten und mobile Bedienung festlegen.
- Abgrenzung zwischen gemeinsamem [GDI](ANHANG_A_GLOSSAR.md#gdi)-Kern und Fachbereichserweiterungen schärfen.

## Dokumentationsqualität

- [A01](04_ENTSCHEIDUNGEN.md#a01)–[A39](04_ENTSCHEIDUNGEN.md#a39) anhand der ursprünglichen Gesprächsprotokolle bei Verfügbarkeit einzeln gegenprüfen; die Erstfassung ist eine konsolidierte Zusammenfassung, keine vollständige Transkription.
- Anforderungen mit überprüfbaren Akzeptanzkriterien ergänzen, wenn die jeweiligen Piloten konkret werden.
- Für die von IT betreibbaren Varianten die offenen Aufwandsannahmen zu Einrichtung, Betrieb und Qualifizierung ergänzen.
- Beschlossene Architektur und technische Vorzugsvarianten stets unterscheiden.

Bei der Pilotkonkretisierung Datenschutz, Lizenzbedingungen und interne Sicherheitsvorgaben für die tatsächlich genutzten Daten und Zugriffspfade klären. Standards dienen als fachliche Orientierung.
