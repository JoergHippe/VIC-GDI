# SW-01 – Serverbetriebssystem

**Status:** Erstes Bewertungsgerüst · **Entscheidung:** offen · **Stand:** 04.11.2026  
**Entscheidungsbezug:** [A23](../04_ENTSCHEIDUNGEN.md#a23), [A24](../04_ENTSCHEIDUNGEN.md#a24) · [Methodik](BEWERTUNGSMETHODIK.md)

## 1. Zweck und Abgrenzung

Das Gastbetriebssystem bildet die technische Laufzeitumgebung für Datenbank und GIS-Dienste. Es muss mit den betrieblichen Standards der IT vereinbar, sicher patchbar und wiederherstellbar sein. Für den geplanten On-prem-Betrieb ist **Debian GNU/Linux eine naheliegende Vorzugsrichtung, aber noch nicht durch die IT beschlossen**.

**Abgrenzung:** **Proxmox VE** ist die bevorzugte vorhandene Virtualisierungsplattform, nicht das Gastbetriebssystem. Ob Dienste nativ, gemischt oder containerisiert laufen, ist die **getrennte offene Architekturentscheidung [A24](../04_ENTSCHEIDUNGEN.md#a24)**. Nicht ohne Anlass eine weitere Hypervisor-Evaluation eröffnen.

## 2. Besondere Anforderungen

- **Muss:** PostgreSQL/PostGIS und die konkret benötigten GIS-Dienste in unterstützten, wartbaren Versionen betreiben können.
- **Muss:** IT-fähiger Patch-, Backup-, Restore-, Monitoring- und Sicherheitsbetrieb.
- **Soll:** Möglichst geringe laufende Lizenz- und Administrationskosten bei langfristig guter Wartbarkeit.
- **Offen:** IT-Kompetenz, vorhandene Windows-Server-Lizenzrechte, vorhandene VM-Kapazitäten, Verantwortlichkeiten.

| Muss-Prüfung | Debian GNU/Linux | Windows Server (Bestandsoption) |
|---|---|---|
| Unterstützter Betrieb der konkreten Komponenten | ? | ? |
| IT kann sicheren Betrieb und Wiederherstellung gewährleisten | ? | ? |

**Hinweis:** Die Prüfung ist noch nicht erfolgt; `?` bedeutet **nicht nachgewiesen**, nicht `nicht erfüllt`.

## 3. Kandidaten (noch keine Auswahl)

| Kandidat | Charakter / Prüfansatz | Ausgangsquelle |
|---|---|---|
| **Debian GNU/Linux** | Freies Serverbetriebssystem, bevorzugter Prüfkandidat. | [Projekt-/Herstellerdokumentation](https://www.debian.org/releases/) |
| **Windows Server (Bestandsoption)** | Alternative nur, wenn vorhandene IT-Vorgaben und Lizenzrechte dies stützen. | [Projekt-/Herstellerdokumentation](https://learn.microsoft.com/de-de/windows-server/get-started/) |

## 4. Vergleichsmatrix

Standardisierte Dimensionen und Gewichte nach [Methodik](BEWERTUNGSMETHODIK.md); `0–3` nur nach Quellenprüfung bzw. Test, sonst `?`.

| Dimension (Gewicht) | Debian GNU/Linux | Windows Server (Bestandsoption) |
|---|---:|---:|
| Fachliche/funktionale Eignung (30 %) | ? | ? |
| Integration/Interoperabilität (20 %) | ? | ? |
| Sicherheit/Berechtigungen (15 %) | ? | ? |
| Betrieb/Wartbarkeit (15 %) | ? | ? |
| Reife/Zukunftsfähigkeit (10 %) | ? | ? |
| Kosten/Lizenzen (10 %) | ? | ? |
| **Gesamt (noch nicht berechenbar)** | — | — |
| **Evidenzstand** | E0 | E0 |

## 5. Vor- und Nachteile – vorläufige Prüfhypothesen

**Debian GNU/Linux:** Freie Standardpakete und gute Linux-Server-Integration sind mögliche Vorteile. Linux-Administrationskompetenz und Paketversionsplanung können zusätzliche Aufwände sein. **Noch zu verifizieren:** Konkrete GIS-Paketversionen, Sicherheitsupdates, interne IT-Betriebsfähigkeit.

**Windows Server (Bestandsoption):** Bekannte interne Betriebswerkzeuge könnten ein Vorteil sein; mögliche Serverlizenzkosten und Linux-orientierte GIS-Deployments könnten Nachteile darstellen. **Noch zu verifizieren:** Lizenzabdeckung, PostgreSQL/QGIS-Server-Support, automatisierte Wartbarkeit.

## 6. Bewertung und Empfehlung

**Aktueller Status: Noch keine belastbare Produktempfehlung.** Linux ist als kostengünstige Richtung plausibel, die finale Machbarkeit und eine mögliche Hardware-Aufstockung beurteilt nur die IT.

**Nächster Schritt:** IT-Bestandsstandard und Kompetenzen aufnehmen; Debian und ggf. Windows mit derselben kleinen GDI-Dienstekombination anhand Installation, Updates und Restore vergleichen.

## 7. Quellen und Stand

- [Debian Releases](https://www.debian.org/releases/) – offizielle Doku; Release- und Wartungszweige
- [Debian-Dokumentation](https://www.debian.org/doc/) – offizielle Doku; Installation/Betrieb
- [Microsoft Windows Server](https://learn.microsoft.com/de-de/windows-server/get-started/) – Herstellerdoku; Editionen, Betrieb, Aktivierung; Lizenzbedingungen zusätzlich prüfen

**Quellenstand:** Ausgangslinks am 04.11.2026 zusammengestellt; **keine vollständige Release-, Lizenz-, Sicherheits- oder Praxistestprüfung**. Unabhängige Bewertungen/Erfahrungsberichte und gegebenenfalls PoC-Ergebnisse werden beim echten Vergleich mit Version und Datum ergänzt.
