# Offene Punkte und zurückgestellte Entscheidungen

**Status:** Interner Arbeitsentwurf; Arbeitsvorrat zur geplanten Einführung der VIC-GDI, **keine Umsetzungs- oder IT-Freigabe**. Verbindliche Festlegungen und Status: [Register A01–A39](04_ENTSCHEIDUNGEN.md). Bereits entschiedene Grundsätze werden hier nicht erneut verhandelt.

## Arbeitspriorität nach Entscheidungshorizont

**P0–P3 beschreiben ausschließlich den sinnvollen Klärungszeitpunkt, nicht den Beschlussstatus B/G/Z/O.** Muss ein Pilot Sicherheits-, Rechte- oder Wiederherstellungsfragen früher lösen, werden diese vorgezogen. PoC, produktiver Pilot und Dauerbetrieb benötigen jeweils die erforderlichen Freigaben.

| Horizont | Offene Klärung | Auslöser / nächster Schritt |
|---|---|---|
| **P0 – Vorbereitung** | [A39](04_ENTSCHEIDUNGEN.md#a39): Umsetzungs-, Qualifizierungs-, Betriebs- und Hosting-/Bezugsmodell; [A31](04_ENTSCHEIDUNGEN.md#a31): Zuständigkeiten und Vertretungen; Pilot-Ist-Situation | GF/IT beauftragen eine abgegrenzte Ressourcen- und Variantenbewertung; GIS und Fachbereiche liefern echte Anwendungsfälle |
| **P1 – Vor Pilotfreigabe** | [A35](04_ENTSCHEIDUNGEN.md#a35): MVP und Abnahme; [A25](04_ENTSCHEIDUNGEN.md#a25)/[A26](04_ENTSCHEIDUNGEN.md#a26): Identitäten/Rechte; [A27–A29](04_ENTSCHEIDUNGEN.md#a27): TEST/PROD, Backup/Restore, Monitoring; A39-Konkretisierung | Konkreten Pilotablauf definieren, Sicherheits- und Betriebsfähigkeit belegen |
| **P2 – Vor jeweiliger Umsetzung** | [A24](04_ENTSCHEIDUNGEN.md#a24): Bereitstellungsform; [A04](04_ENTSCHEIDUNGEN.md#a04)/[A36](04_ENTSCHEIDUNGEN.md#a36): Projektablage/Migration; [A10](04_ENTSCHEIDUNGEN.md#a10), [A12](04_ENTSCHEIDUNGEN.md#a12), [A13](04_ENTSCHEIDUNGEN.md#a13), [A15](04_ENTSCHEIDUNGEN.md#a15), [A30](04_ENTSCHEIDUNGEN.md#a30): tatsächliche Ausgestaltung | Nur bei bestätigtem Pilotbedarf gezielt prüfen; bei Sicherheitsrelevanz nach P1 vorziehen |
| **P3 – Später/bei Bedarf** | [A37](04_ENTSCHEIDUNGEN.md#a37): Datenlebenszyklus; [A38](04_ENTSCHEIDUNGEN.md#a38): zusätzliche fachliche DB-/QGIS-Validierung; nicht pilotrelevante Funktionen | Konkreter Anlass oder fachlich begründeter Nutzen |

## Architekturentscheidungen und technische Prüfaufträge

| Bezug | Konkret noch offen | Prüfschritt / Grenze |
|---|---|---|
| [A04](04_ENTSCHEIDUNGEN.md#a04)/[A36](04_ENTSCHEIDUNGEN.md#a36) | PostgreSQL als QGIS-Projektablage; geeignete Bestandsprojekte, Datenpfade und Rechte | Ein repräsentatives Fachprojekt mit Vektordaten und Rasterreferenz, zwei Arbeitsplätzen und getrennten Rollen testen: Speichern/Öffnen, berechtigtes und verweigertes Ändern, konkurrierende Projekt- **und getrennt davon Datenänderungen**, Wiederherstellung und ggf. QGIS-Server-Veröffentlichung. Inventar, Pfad-/Abhängigkeitsprüfung, Rückfallweg und fachliche Abnahme für Migration erfassen. **Keine neue Ablageentscheidung vorwegnehmen.** |
| [A15](04_ENTSCHEIDUNGEN.md#a15) | Umfang und Pflege eines internen Metadatenkatalogs | Echte Suchfälle und Mindestfelder priorisieren. Automatisch ableitbare technische Metadaten von redaktionellen Angaben trennen; je Feld führende Quelle, Zuständigkeit und Konfliktbehandlung festlegen. Eigene Katalogsoftware/OGC-Schnittstelle nur bei nachgewiesenem Bedarf ([SW-04](software/04_METADATENKATALOG.md)). |
| [A10](04_ENTSCHEIDUNGEN.md#a10) | QGIS-Server-Eignung und erforderliche OGC-Funktionen | Bei Webbedarf repräsentative Pilotkarte und Zugriffsrechte testen ([SW-02](software/02_KARTENSERVER.md)). |
| [A12](04_ENTSCHEIDUNGEN.md#a12)/[A26](04_ENTSCHEIDUNGEN.md#a26) | **Berechtigungsmodell offen**, Verfahren/Formate/CRS fachlich festgelegt | Zuerst reale Nutzerrollen, Bestände und Zugriffspfade erheben. Danach Positiv-/Negativtests aller Exportwege, Objektselektion/Clipping (insb. Rechte über Auswahlgebietsgrenzen hinaus), GPKG/GeoJSON 2008 und optional RFC 7946, DXF/CSV und EPSG:25832/25833/3068 durchführen. Nicht abgesicherte Wege nicht produktiv freischalten ([SW-06](software/06_GEODATENAUSZUG.md)). |
| [A13](04_ENTSCHEIDUNGEN.md#a13) | QField-Rückübertragung, Offline-/Konfliktverhalten, Sicherheitsfreigabe | Gehosteten Cloudweg und lokalen USB-Transfer anhand derselben BB-Beispieldaten vergleichen; Synchronisation ist keine fachliche Freigabe ([Pilot](05_PILOTKONKRETISIERUNG.md#mobile-erfassung-und-datenaustausch)). |
| [A24](04_ENTSCHEIDUNGEN.md#a24) | Natives VM-, Hybrid- oder Container-Deployment | IT bewertet Betriebskompetenz, Wartung, Sicherheit, Backup und Kosten. Keine Variante vorab festlegen. |
| [A25](04_ENTSCHEIDUNGEN.md#a25)–[A29](04_ENTSCHEIDUNGEN.md#a29) | Unternehmens-SSO/IdP, Rollenmatrix inkl. direktem DB-Zugriff, TEST/PROD, RPO/RTO, Restore, GIS-Monitoring | Vor Pilotfreigabe mit IT konkretisieren; Rechte, Sicherung und Wiederherstellung mit realen Testfällen nachweisen. |
| [A30](04_ENTSCHEIDUNGEN.md#a30)/[A31](04_ENTSCHEIDUNGEN.md#a31) | Git-/Bereitstellungsabläufe, Verantwortlichkeiten/Vertretungen | Einfache Verfahrens- und Zuständigkeitsmatrix GIS/IT vereinbaren, vorhandene Werkzeuge nutzen. |
| [A35](04_ENTSCHEIDUNGEN.md#a35) | Erster GDI- und Pilot-MVP, nachvollziehbare Erfolgskriterien | Je Pilot ein bis zwei reale Abläufe priorisieren; fachliche Abnahme festlegen ([Pilotkonkretisierung](05_PILOTKONKRETISIERUNG.md)). |
| [A37](04_ENTSCHEIDUNGEN.md#a37)/[A38](04_ENTSCHEIDUNGEN.md#a38) | Lebenszyklusdetails und **zusätzliche** fachliche Validierungsregeln | Bewusst zurückgestellt; weder Option B noch ein vollständiges Regelwerk beschlossen. **Grundlegende Datenintegrität und Sicherheit bleiben Pflicht.** |

## Offene Organisationsentscheidung: Umsetzung und Betrieb

**[A39](04_ENTSCHEIDUNGEN.md#a39) bleibt vorrangig und offen.** Umsetzung (A1–A3/B1/C1–C2), rollenbezogener Wissensaufbau, Betrieb (D1–D3) und Hosting/Bezug (H1–H4) **getrennt** vergleichen. H1 = eigene Infrastruktur, H2 = gemietete Infrastruktur mit eigener GDI, H3 = betreute Mietinfrastruktur, H4 = GDIaaS (früher C3). Mietserver bedeuten **nicht automatisch externen GIS-Betrieb**.

GIS/IT prüfen wenige realistische Kombinationen auf gleichen Kosten- und Zeithorizont: vorhandene Proxmox-Ressourcen, Cloud-/Netz-/Transferkosten, Kompetenzen, Vertretung, Backup/Restore, Sicherheit, Portabilität und Ausstieg. **GF und IT** entscheiden im jeweiligen Verantwortungsbereich; [A3/B1 mit D2](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md) ist nur eine Prüfrichtung. Führender [Variantenvergleich](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md).

## Öffentliches GitHub-Repository: Freigabe- und Lizenzklärung

- **Inhalte:** Veröffentlichungsfreigabe für interne und organisatorische Angaben prüfen; bei vertraulichen Inhalten auch Git-Historie berücksichtigen.
- **Nachnutzung:** Fehlende `LICENSE` bedeutet **keine** automatische Open-Source-Freigabe der Dokumentation; Rechteklärung durch zuständige Unternehmensstellen.
- **Fremdinhalte:** Vorlagen, Bilder und fremde Textteile auf zulässige Weitergabe prüfen.

## Kosten- und Lizenzklärung mit IT

- Die [Kernsoftware- und Lizenzübersicht](software/README.md#lizenz--und-kostenüberblick-gdi-kern) für die tatsächlich eingesetzten Versionen prüfen: **keine zusätzlichen Lizenzgebühren für den freien GDI-Kern**, aber geltende Open-Source-Pflichten und Rechte an Fremddaten.
- **Proxmox:** vorhandene Hosts/CPU-Sockel, Subskriptionen, Update-Repository, Support und Backup prüfen. Eine kostenpflichtige Subskription ist **keine zwingende Nutzungslizenz**.
- **Ressourcen:** IT prüft auf Basis der echten Pilotlast RAM, CPU, Speicher, Sicherung und ggf. Hardwarebedarf; zusätzliche Beschaffung weder unterstellen noch ausschließen.
- **Optionale Dienste:** Gehostete QFieldCloud, Miet-/Managed-Hosting, externer Betrieb und Support mit ihren eigenen Gebühren getrennt bewerten.
- **Gesamtwirtschaftlichkeit:** Einmalige interne/externe Aufwände, Schulung, Wartung, Infrastruktur, Laufkosten und optionalen Bezug getrennt schätzen. Keine Einsparungen ohne Ist-Daten behaupten. Führend: [A39-Kostenrahmen](06_UMSETZUNGS_UND_BETRIEBSMODELLE.md#kostenrahmen-und-lizenzabgrenzung).

## Fachliche Konkretisierung

Fachbereiche legen für die Pilotfälle reale Nutzer, Datenbestände, Verantwortliche, Quelle/Aktualität, mögliche gemeinsame Daten, Projektbezug, Bedienanforderungen und fachliche Abnahmekriterien fest. Suchfelder, Datenrechte, CAD-/GIS-Schnittstellen, mobile Nutzung und einfache Webansichten nur soweit vertiefen, wie der ausgewählte Ablauf sie braucht. [Erhebungsleitfaden](05_PILOTKONKRETISIERUNG.md).

## Dokumentationsqualität

- A01–A39 bei Verfügbarkeit mit ursprünglichen Gesprächsnotizen abgleichen; Register ist eine **Konsolidierung**, kein vollständiges Transkript.
- Spätere Detailanforderungen nur mit bestätigten Pilotfällen und überprüfbaren Kriterien präzisieren.
- Beschlossene Grundlagen, Prüfhypothesen und formale GF-/IT-Freigaben sauber auseinanderhalten; Datenschutz, interne IT-Vorgaben und Daten-/Lizenzrechte vor tatsächlicher Nutzung prüfen.
