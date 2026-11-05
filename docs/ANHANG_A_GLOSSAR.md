# Glossar – VIC-GDI

**Status:** Interner Arbeitsentwurf. Kurze, projektbezogene Erläuterungen; Links führen zu anerkannten Referenzen. Kein vollständiges GIS-Lexikon.

**Pflege:** Nur für die Zielgruppen erklärungsbedürftige Begriffe aufnehmen; beim ersten Auftreten je Dokument verlinken, nicht jedes Vorkommen. Bei Bedarf Definitionen aktualisieren, ohne daraus ein umfassendes Lexikon zu machen.

<a id="produkte-und-komponenten"></a>

<a id="ad"></a>

## AD DS (Active Directory Domain Services)

Windows-Verzeichnisdienst für Domänen, Unternehmensidentitäten und Gruppen. Für VIC-GDI ist zu klären, welche vorhandenen Gruppen und Anmeldewege für den Browser und für den direkten Datenbankzugriff nutzbar sind.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Active_Directory)

<a id="aoi"></a>

## AOI (Area of Interest)

Räumlich abgegrenztes Interessengebiet, etwa die optionale Projektabgrenzung. Ein Projekt kann auch ohne eigene räumliche Abgrenzung geführt werden.

<a id="api"></a>

## API

Programmierschnittstelle zwischen Anwendungen und Diensten.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Programmierschnittstelle)

<a id="bbox"></a>

## BBox (Bounding Box)

Rechteckige räumliche Umgrenzung für Suche oder Export. Sie beschreibt die äußere Ausdehnung. Für den exakten Zuschnitt entlang einer unregelmäßigen Grenze wird die tatsächliche Grenzgeometrie benötigt.

<a id="bim"></a>

## BIM (Building Information Modeling)

Methode zur modellbasierten Zusammenarbeit mit digitalen Bauwerksinformationen.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Building_Information_Modeling)

<a id="cad"></a>

## CAD (Computer-Aided Design)

Rechnergestütztes Konstruieren und Zeichnen, etwa für technische Pläne und Modelle.

<a id="ci-cd"></a>

## CI/CD

Automatisiertes Prüfen und Bereitstellen von Softwareänderungen.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/CI/CD)

<a id="cog"></a>

## COG (Cloud Optimized GeoTIFF)

Für effizienten teilweisen Zugriff organisiertes GeoTIFF. Bei geeignetem Speicher und Client lassen sich benötigte Bildausschnitte lesen, ohne vorher die gesamte Datei zu laden.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Open_Geospatial_Consortium)

<a id="crs"></a>

## CRS (Coordinate Reference System)

Koordinatenreferenzsystem zur eindeutigen räumlichen Zuordnung. Es legt fest, wie Koordinaten einem Ort zugeordnet werden. Bei der Übernahme von Daten ist der Höhenbezug gesondert zu beachten, wenn Höhenwerte verwendet werden.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Koordinatenreferenzsystem)

<a id="csv"></a>

## CSV (Comma-Separated Values)

Textformat für tabellarische Daten, dessen Felder durch ein Trennzeichen getrennt werden.

<a id="debian"></a>

## Debian

Linux-Distribution und möglicher Kandidat für den Serverbetrieb.

Weiterführend · [Produktseite](https://www.debian.org/)

<a id="docker"></a>

## Docker

Werkzeuge zum Paketieren und Betreiben von Diensten in Containern. Für VIC-GDI ist offen, welche Dienste nativ und welche in Containern laufen. Container können dabei innerhalb einer virtuellen Maschine betrieben werden.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Docker_(Software))

<a id="etl"></a>

## ETL (Extract, Transform, Load)

Daten aus Quellen übernehmen, umwandeln und in Zielsysteme laden. Ein typischer Import übernimmt Quelldaten, passt Felder oder Koordinaten an und lädt das Ergebnis in die Zieldatenbank. In VIC-GDI beginnt die Automatisierung mit überschaubaren Importabläufen und Skripten.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/ETL-Prozess)

<a id="gdi"></a>

## GDI (Geodateninfrastruktur)

Eine Geodateninfrastruktur organisiert das geordnete Führen, Wiederfinden und Bereitstellen raumbezogener Informationen sowie die dazugehörigen Verantwortlichkeiten und Rechte. Sie ist **kein einzelnes Programm**. In VIC-GDI sollen Fachbereiche geeignete gemeinsame Daten verlässlich nutzen können. [Einsteigererklärung mit einfachem Schaubild](01_PROJEKTKONZEPT.md#was-ist-eine-geodateninfrastruktur--und-wie-funktioniert-sie).

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Geodateninfrastruktur)

<a id="gdiaas"></a>

## GDIaaS (GDI as a Service)

Beim Anbieter gehostete und betriebene Geodateninfrastruktur als Dienstleistung. Der gebuchte Funktionsumfang und die Administrations-/Datenzugriffsmöglichkeiten sind vertraglich festgelegt. VIC-GDI führt dieses Bezugsmodell unter **H4** ([A39](04_ENTSCHEIDUNGEN.md#a39)); nicht mit einer selbst betriebenen GDI auf gemieteten Servern (**H2**) verwechseln.

<a id="geodaten"></a>

## Geodaten

Raumbezogene digitale Informationen, die mithilfe von Geografischen Informationssystemen (GIS) erfasst und analysiert werden. Werden über Geodateninfrastrukturen standardisiert bereitgestellt und vernetzt. Typische Beispiele sind Liegenschaftskataster, Digitale Geländemodelle (DGM), Topografische Karten oder Luftbilder.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Geodaten)

<a id="extract"></a>

## Geodatenauszug (Extract)

Bereitstellung ausgewählter, **berechtigter** Geodaten für einen bestimmten Ausschnitt oder Verwendungszweck. VIC-GDI sieht **vollständige Objektselektion als Standard** und **geometrisches Clipping als zusätzliche Option** vor; ein eigener Exportserver ist nicht verpflichtend. Beide Verfahren dürfen bestehende Zugriffsbeschränkungen nicht umgehen.

<a id="geojson"></a>

## GeoJSON

JSON-basiertes, offenes Austauschformat für Vektorgeometrien und Attribute.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/GeoJSON)

<a id="geopackage"></a>

## GeoPackage (GPKG)

Offenes, SQLite-basiertes Format für Geodaten in einer Datei. Eine Datei kann mehrere räumliche Tabellen enthalten und eignet sich für die Weitergabe eines abgegrenzten Datenbestands.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/GeoPackage)

<a id="geoserver"></a>

## GeoServer

GeoServer ist eine freie Mapserver-Software. Sie zeichnet sich aus durch Konformität zu Standards des Open Geospatial Consortiums.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/GeoServer)

<a id="geotif"></a>

## GeoTIFF

TIFF-Rasterformat mit Angaben zur räumlichen Lage und zum Koordinatenbezug.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/GeoTIFF)

<a id="gis"></a>

## GIS (Geoinformationssystem)

Software und Verfahren zur Bearbeitung, Analyse und Darstellung räumlicher Daten. Im Arbeitsalltag lassen sich damit beispielsweise Leitungen erfassen, Flächen auswerten und die Ergebnisse auf einer Karte darstellen.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Geoinformationssystem)

<a id="git"></a>

## Git

Verteilte Versionsverwaltung für Quelltext und geeignete Konfigurationsdateien. In VIC-GDI dient Git zur Pflege der Dokumentation und geeigneter technischer Ressourcen wie Skripte und Stildateien.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Git)

<a id="gnss"></a>

## GNSS (Global Navigation Satellite System)

Sammelbegriff für satellitengestützte Positionsbestimmung, etwa mit GPS oder Galileo. In der Baubetreuung liefert der Empfänger die Position für die Erfassung. Welche Lage- und Höhengenauigkeit benötigt wird, hängt vom jeweiligen Arbeitsablauf ab.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Globales_Navigationssatellitensystem)

<a id="ha"></a>

## HA (High Availability)

Maßnahmen für hohe Verfügbarkeit trotz einzelner Ausfälle.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Hochverf%C3%BCgbarkeit)

<a id="happy_mini_q"></a>

## HAPPY MINI Q

GNSS-Empfänger für die mobile Positionserfassung mit QField. Die Begleit-App HAPPY Q unterstützt Einrichtung und Verbindung.

Weiterführend · [Produktseite](https://happy-q.com/)

<a id="idp"></a>

## IdP (Identity Provider)

Dienst zur Authentifizierung und Bereitstellung von Identitätsinformationen. Er bestätigt einer Anwendung die Identität einer Person. Die Anwendung oder der jeweilige Dienst entscheidet anhand seiner Berechtigungsregeln, welche Daten sie nutzen darf.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Identitätsanbieter)

<a id="iaas"></a>

## IaaS (Infrastructure as a Service)

Gemietete IT-Infrastruktur wie virtuelle Maschinen, Speicher und Netzkomponenten. Der Hoster verwaltet die vertraglich vereinbarte Infrastruktur; Betriebssystem, Datenbanken und GIS-Anwendungen liegen bei unverwalteten Angeboten weiterhin in der Verantwortung des Kunden bzw. seiner beauftragten Dienstleister. Bei VIC-GDI entspricht dies vor allem **H2** ([A39](04_ENTSCHEIDUNGEN.md#a39)). Siehe [Shared Responsibility bei IaaS](https://aws.amazon.com/de/compliance/shared-responsibility-model/).

<a id="itsm"></a>

## ITSM (IT-Service-Management)

Organisation und Betrieb von IT-Diensten, etwa Support, Störungsbehebung und Änderungen. Für VIC-GDI sollen vorhandene Supportwege genutzt und Zuständigkeiten zwischen IT und GIS geklärt werden.

<a id="lizmap"></a>

## Lizmap Web Client

Webkartenanwendung auf Basis von QGIS Server. Kandidat für die Webpublikation.

Weiterführend · [Produktseite](https://www.3liz.com/en/lizmap.html)

<a id="ims"></a>

## Mapserver

Mapserver, auch Internet Map Server (IMS) ist eine Server-Software, die auf Geodaten spezialisierte Webservices (Geodienste) bereitstellt und somit die Verarbeitung von Kartenausschnitten und ortsbezogenen Informationen ermöglicht.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Mapserver)

<a id="mapserver"></a>

## MapServer

MapServer ist ein freies Mapserver-Projekt der Open Source Geospatial Foundation (OSGeo), als ehemaliges Projekt der University of Minnesota (UMN) auch bekannt unter dem Namen UMN Mapserver oder UMN MapServer.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/MapServer)

<a id="entra-id"></a>

## Microsoft Entra ID

Cloud-Identitätsdienst, unter anderem für die Anmeldung bei Microsoft 365. Eine Kopplung mit AD DS ist möglich.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Microsoft_Entra_ID)

<a id="mvp"></a>

## MVP (Minimum Viable Product)

Kleinster sinnvoll nutzbarer Funktionsumfang zum frühen Praxistest. In VIC-GDI umfasst der erste nutzbare Stand einen konkreten Pilotablauf samt sicherem Zugriff und Wiederherstellbarkeit. Weitere Funktionen folgen dem Bedarf dieses Ablaufs.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Minimum_Viable_Product)

<a id="oauth"></a>

## OAuth

Standardrahmen zur delegierten Autorisierung. Es regelt, wie eine Anwendung Zugriff auf geschützte Ressourcen erhält. Für eine Anmeldung kann darauf OpenID Connect aufsetzen.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/OAuth)

<a id="ogc"></a>

## OGC (Open Geospatial Consortium)

Gemeinnützige Organisation für interoperable Geodatenstandards.

Weiterführend · [OGC](https://www.ogc.org/)

<a id="oidc"></a>

## OIDC (OpenID Connect)

Identitätsschicht für Anmeldung auf Basis von OAuth 2.0. Eine Anwendung kann damit nach der Anmeldung Identitätsinformationen vom Identitätsdienst erhalten. Die konkrete Integration für den Webzugriff ist mit der IT abzustimmen.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/OpenID_Connect)

<a id="poc"></a>

## PoC (Proof of Concept)

Begrenzter technischer Machbarkeitstest. Ein Beispiel wäre der Nachweis, dass ein zentral gespeichertes QGIS-Projekt mit zwei unterschiedlichen Rollen geöffnet und kontrolliert bearbeitet werden kann.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Proof_of_Concept)

<a id="postgis"></a>

## PostGIS

Räumliche Erweiterung der Datenbank PostgreSQL. Die Erweiterung stellt räumliche Datentypen und Abfragen bereit, etwa für die Suche nach Objekten innerhalb eines Gebiets. In VIC-GDI bildet sie die Basis für gemeinsam genutzte Vektordaten.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/PostGIS)

<a id="postgresql"></a>

## PostgreSQL

Relationales Open-Source-Datenbanksystem. Sie verwaltet Tabellen, Rollen und Transaktionen. Für räumliche Daten wird sie in VIC-GDI mit PostGIS erweitert.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/PostgreSQL)

<a id="proxmox"></a>

## Proxmox VE

Plattform zur Virtualisierung von Servern und Containern. Für VIC-GDI ist die vorhandene Plattform der bevorzugte Ausgangspunkt für das Hosting. Die genaue Verteilung von Diensten auf virtuelle Maschinen und Container ist offen.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Proxmox_VE)

<a id="qfield"></a>

## QField

Mobile GIS-Anwendung für QGIS-basierte Erfassungsabläufe. Die Baubetreuung nutzt die Anwendung auf Tablets und Smartphones. Cloud-Austausch und lokale Speicherung mit anschließender USB-Übertragung werden als zwei Wege für den Datentransfer betrachtet.

Weiterführend · [QField](https://qfield.org/)

<a id="qgis"></a>

## QGIS

Freies Desktop-GIS zur Erfassung, Analyse und Darstellung von Geodaten. Fachanwender nutzen QGIS Desktop am Arbeitsplatz, um Datenquellen einzubinden, Layer zu gestalten und Projekte zu bearbeiten.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/QGIS)

<a id="qgis_server"></a>

## QGIS Server

Serverkomponente zur Bereitstellung von QGIS-Projekten als standardisierte Karten- und Datendienste. Er liefert Karten oder Daten an andere Anwendungen, etwa einen Webviewer. Sein Einsatz im Pilot hängt davon ab, ob Webkarten benötigt werden.

Weiterführend · [QGIS Server](https://qgis.org/project/overview/)

<a id="qwc2"></a>

## QGIS Web Client 2 (QWC2)

Webclient für QGIS Server und Kandidat für die Webpublikation.

Weiterführend · [GitHub](https://github.com/qgis/qwc2)

<a id="qml"></a>

## QML (QGIS-Stildatei)

Datei zum Speichern von QGIS-Layerdarstellungen; hier nicht die Qt-Oberflächensprache.

Weiterführend · [QGIS-Dokumentation](https://docs.qgis.org/)

<a id="rpo-rto"></a>

## RPO/RTO

RPO (Recovery Point Objective) bezeichnet den maximal tolerierten Datenverlustzeitraum. RTO (Recovery Time Objective) bezeichnet die maximal tolerierte Wiederherstellungsdauer. Ein RPO von vier Stunden bedeutet beispielsweise, dass höchstens vier Stunden an Änderungen verloren gehen dürfen. Ein RTO von acht Stunden bedeutet, dass der Dienst innerhalb von acht Stunden wieder verfügbar sein soll. Die konkreten Ziele legt VIC-GDI mit der IT fest.

Weiterführend · [Wikipedia](https://en.wikipedia.org/wiki/Recovery_point_objective)

<a id="shapefile"></a>

## Shapefile

Vektordatenformat, bei dem Geometrien und Attribute in mehreren zusammengehörigen Dateien abgelegt sind.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Shapefile)

<a id="snapshot"></a>

## Snapshot (Datenstand)

Zu einem Zeitpunkt fixierter, nachvollziehbarer Datenbestand. Ein solcher Stand kann bei externen Basisdaten sinnvoll sein, wenn eine spätere Auswertung mit derselben Datengrundlage nachvollziehbar bleiben soll.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Schnappschuss_(Informationstechnik))

<a id="sso"></a>

## SSO (Single Sign-on)

Anmeldung über eine zentrale Identität statt separate Konten je Anwendung. Eine bestehende Anmeldung kann für mehrere angebundene Anwendungen genutzt werden. Welche Daten die Person dort sehen oder bearbeiten darf, richtet sich weiterhin nach ihren Berechtigungen.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Single_Sign-on)

<a id="utm"></a>

## UTM

Weltweit verwendetes kartesisches Kartenkoordinatensystem in Zonen.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/UTM-Koordinatensystem)

<a id="vm"></a>

## VM (Virtuelle Maschine)

Virtueller Rechner mit eigenem Betriebssystem, der auf einem Host betrieben wird.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Virtuelle_Maschine)

<a id="vpn"></a>

## VPN (Virtual Private Network)

Geschützte Netzwerkverbindung für den Zugriff auf interne Systeme.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Virtual_Private_Network)

<a id="webviewer"></a>

## Webviewer

Kartenanwendung im Browser ohne lokale GIS-Installation. Er richtet sich etwa an Projektbeteiligte, die Karten ansehen oder Informationen abfragen möchten. Für VIC-GDI ist er vorgesehen, wenn ein priorisierter Pilotablauf ihn benötigt.

<a id="wms"></a>

## WMS (Web Map Service)

OGC-Dienst zur Bereitstellung gerenderter Kartenbilder. Ein Client fordert für einen Ausschnitt und ausgewählte Ebenen ein Kartenbild an. Für die Weiterverarbeitung der zugrunde liegenden Vektorgeometrien braucht er einen geeigneten Datendienst oder Geodatenauszug.

Weiterführend · [Wikipedia](https://de.wikipedia.org/wiki/Web_Map_Service)
