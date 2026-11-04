# Softwarelizenzen und Kostenrahmen – VIC-GDI

**Stand:** 04.11.2026 · **Status:** Bewertungsgrundlage für Geschäftsführung und IT; keine Budgetfreigabe, keine abschließende Stückliste oder Rechtsprüfung.

## Kernaussage

**Der vorgesehene GDI-Kern lässt sich mit freier Open-Source-Software ohne zusätzliche Softwarelizenzgebühren aufbauen und gewerblich betreiben.** Für die im Konzept bevorzugten Komponenten sind weder kostenpflichtige Nutzerlizenzen noch zwingende Hersteller-Subskriptionen Voraussetzung. Die endgültige Auswahl, konkrete Pakete und Versionen werden erst mit der IT/Pilotplanung geprüft. Dies ist **keine Aussage über einen kostenfreien Gesamtbetrieb**.

## Einordnung der vorgesehenen Software

| Ebene | Software / Status im Konzept | Zusätzliche Softwarelizenzkosten | Hinweis |
|---|---|---|---|
| GIS-Arbeitsplatz | [QGIS Desktop](https://qgis.org/license/) – fachlicher Kern | **Keine** | Freie Software (GPL); keine nutzerbezogene Lizenzgebühr. |
| Räumliche Datenbank | [PostgreSQL](https://www.postgresql.org/about/licence/) + [PostGIS](https://postgis.net/documentation/faq/gpl-license/) – vorgesehener Kern | **Keine** | PostgreSQL-Lizenz bzw. GPLv2; betriebliche Nutzung ohne Lizenzgebühr. |
| Kartenbereitstellung | [QGIS Server](https://qgis.org/download/) – bevorzugt, PoC offen | **Keine** | Freier Bestandteil des QGIS-Ökosystems; Betriebsfähigkeit noch zu validieren. |
| Browserkarten | [Lizmap](https://github.com/3liz/lizmap-web-client) oder [QWC2](https://github.com/qgis/qwc2) – Kandidaten | **Keine für die genannten Open-Source-Editionen** | Auswahl, Funktionsumfang, Betrieb und eingesetzte Erweiterungen offen. |
| Mobile Datenerfassung | [QField](https://docs.qfield.org/get-started/license/) – in der Baubetreuung eingesetzt | **Keine für die App** | Synchronisation und ggf. benötigte Zusatzdienste gesondert betrachten. |
| Serverbetriebssystem | [Debian GNU/Linux](https://www.debian.org/intro/why_debian) – Kandidat | **Keine für freie Standardpakete** | Auswahl und Administration liegen bei der IT; einzelne Zusatzpakete können andere Bedingungen haben. |
| Konfiguration/Versionierung | [Git](https://git-scm.com/about/free-and-open-source) – für geeignete Ressourcen vorgesehen | **Keine für Git selbst** | Hosting, kommerzielle Plattformfunktionen und Administration gegebenenfalls gesondert. |
| Virtualisierungsplattform | [Proxmox VE](https://www.proxmox.com/de/produkte/proxmox-virtual-environment/erste-schritte) – vorhandene Infrastruktur bevorzugt | **Keine zwingende Lizenzgebühr** | Kostenpflichtige Subskription für Enterprise-Repository/Herstellersupport optional, siehe unten. |
| Containerbetrieb, falls gewählt | [Docker Engine](https://docs.docker.com/engine/) unter Linux – mögliche Technik, **A24 offen** | **Keine für die Open-Source-Engine** | Nicht mit dem separat lizenzierten Docker Desktop gleichsetzen. |

Die Tabelle beschreibt **vorgesehene oder geprüfte Komponenten**, nicht eine bereits beschlossene vollständige Softwarestückliste. Freie Software ist lizenzrechtlich nicht „lizenzfrei“: jeweilige Open-Source-Lizenzpflichten und Hinweise sind einzuhalten.

## Proxmox VE: kostenfrei nutzbar, Subskription optional

- **Proxmox VE selbst ist Open Source (GNU AGPLv3)** und auch im professionellen Produktivbetrieb ohne Kauf einer Softwarelizenz nutzbar. Die wesentlichen Funktionen sind nicht durch kostenpflichtige Lizenzstufen gesperrt.
- **Ohne Subskription:** Nutzung und Updates sind über das `pve-no-subscription`-Repository möglich. Dieses ist **nicht** das vom Hersteller für den produktiven Betrieb empfohlene Enterprise-Repository.
- **Mit optionaler kostenpflichtiger Subskription:** Zugang zum stärker geprüften **Enterprise-Repository** und, je nach Stufe, Herstellersupport. Für produktionskritische Infrastruktur ist dies eine **Betriebs-/Risikofrage**, keine technische oder rechtliche Lizenzpflicht zum Einsatz von Proxmox VE.
- **Kostenmodell bei Neubeschaffung:** Abrechnung nach belegten physischen CPU-Sockeln je Host; bei Clustern sind die beteiligten Hosts zu berücksichtigen. Konkrete Stufe und aktuelle Preise erst bei Bedarf mit IT/Einkauf prüfen; keine pauschale jährliche Zusatzgebühr der GDI unterstellen.
- **Vorhandene Proxmox-Installation:** Zuerst klären, ob vorhandene Hosts, Kapazitäten, Backups und ggf. bestehende Subskriptionen die GDI bereits abdecken. Eine bestehende Subskription muss **nicht automatisch** wegen zusätzlicher GDI-VMs erweitert werden; neue Hosts/Sockel oder geänderte Betriebsanforderungen können dagegen Mehraufwand auslösen.

Herstellerquellen: [Kostenloser Einsatz](https://www.proxmox.com/de/produkte/proxmox-virtual-environment/erste-schritte), [Subskriptionsmodelle und Bedingungen](https://www.proxmox.com/en/products/proxmox-virtual-environment/pricing), [Repository-/Betriebshinweise](https://pve.proxmox.com/pve-docs/pve-admin-guide.html).

## Kosten, die trotz kostenfreier Kernsoftware entstehen können

| Kostenfeld | Einordnung |
|---|---|
| **Einmalige interne Aufwände** | Ist-Aufnahme, Installation, Anbindung, Datenmigration, Datenmodelle, Tests, Berechtigungen, Dokumentation und Einführung. |
| **Laufender Personal-/Betriebsaufwand** | IT-/GIS-Administration, Sicherheitspatches, Datenpflege, Monitoring, Datensicherung, Restore-Tests, Support und Weiterentwicklung. |
| **Qualifizierung** | Einarbeitung, Schulung und Vertretung; siehe [A33](04_ENTSCHEIDUNGEN.md#a33). |
| **Infrastruktur (Bedarf offen)** | Eventuell müssen bestehende Ressourcen aufgestockt werden, etwa Speicherplatz, RAM, CPU-Leistung, Backup-Speicher oder Serverhardware. **Nur die IT kann anhand der verfügbaren Infrastruktur und des konkretisierten Pilotbedarfs feststellen, ob dies nötig ist und welche Kosten entstehen.** Zusätzlicher Netzwerk- und Energiebedarf ist ebenfalls bei Bedarf zu bewerten. Keine Hardware-Neubeschaffung vorwegnehmen. |
| **Optionale Supportleistungen** | Proxmox-Subskription, externer IT-/GIS-Support, Schulungen, Wartungsleistungen; nur bei fachlich/betrieblich begründetem Bedarf. |
| **Optionale Zusatzangebote und Daten** | Gehostete Cloud-Dienste, kommerzielle Add-ons, Karten-/Geodaten-Abonnements, API-Nutzungsgebühren oder zusätzliche proprietäre Produkte. **Nicht Teil der pauschalen Null-Lizenzkosten-Aussage.** |

**Besonders abzugrenzen:**

- **QField-App ≠ QFieldCloud:** Die QField-App ist kostenlos. Für die [gehostete QFieldCloud](https://qfield.cloud/pricing) existiert ein begrenzter kostenloser Tarif neben kostenpflichtigen Organisations-/Synchronisationsfunktionen. Eine selbst gehostete Open-Source-Variante ist möglich, verursacht aber Betriebsaufwand. Für den Pilot sind Cloud- und lokaler USB-Transfer noch zu vergleichen; keine bezahlte Cloudlösung ist beschlossen ([A13](04_ENTSCHEIDUNGEN.md#a13)).
- **Docker Engine ≠ Docker Desktop:** Die Linux-Engine ist Open Source; [Docker Desktop](https://docs.docker.com/subscription-billing/desktop-license/) kann im gewerblichen Unternehmenseinsatz abhängig von Größe/Umsatz kostenpflichtig sein. Für einen Linux-Serverbetrieb ist Docker Desktop nicht erforderlich. Die Containerentscheidung [A24](04_ENTSCHEIDUNGEN.md#a24) bleibt offen.
- **Vorhandene Unternehmenssoftware:** Windows, AD/Entra, M365, VPN, Fachsoftware sowie vorhandene mobile Geräte/GNSS-Hardware sind keine neu zu beschaffenden freien GDI-Kernprodukte. Bestehende Vertrags-, Kapazitäts- und Lizenzbedingungen bleiben unberührt; Erweiterungen sind einzeln zu prüfen.
- **Datenlizenzen:** Gebühren und Nutzungsrechte für externe Geodaten, Basiskarten, Luftbilder oder Drittanbieter-APIs sind von der Softwarelizenz unabhängig.

## Prüfauftrag für IT und Projektplanung

1. Für den tatsächlich eingesetzten GDI-MVP Softwarestückliste mit Version, Bezugsquelle, Lizenz und ggf. Drittanbieterkomponenten bestätigen; Open-Source-Pflichten, insbesondere bei Änderungen und Weitergabe/Bereitstellung, berücksichtigen.
2. Proxmox-Bestandsinfrastruktur, belegte CPU-Sockel, vorhandene Subskription, Repo- und Support-Strategie, Kapazitätsreserven und zusätzliche Betriebs-/Backup-Kosten feststellen.
3. Bei mobilen Pilotabläufen mögliche Kosten eines Synchronisationsdienstes (insbesondere QFieldCloud) **erst nach Variantenvergleich** bewerten.
4. Für die Geschäftsführung getrennt ausweisen: **Softwarelizenzgebühren der ausgewählten Kernkomponenten**, **einmaliger Aufbauaufwand**, **laufende Betriebs-/Personalkosten**, **optionale externe Leistungen**.

Diese Kosteneinordnung trifft **keine neue Architekturentscheidung**. Insbesondere bleiben [A23](04_ENTSCHEIDUNGEN.md#a23) (Hostingpräferenz) und [A24](04_ENTSCHEIDUNGEN.md#a24) (Deployment offen) unverändert. Technische Details siehe [IT-Briefing](BRIEFING_IT.md); Managementkurzfassung siehe [GF-Briefing](BRIEFING_GESCHAEFTSFUEHRUNG.md).
