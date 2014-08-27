#WFS-WMS AdV-Profile und Produktspezifikationen

__Worum geht's?__

Profile (AdV)
Spezifikationen ansehen

Wir müssen uns um die Spezifikationen kümmern
WMS Darstellung, Entscheidungen müssen getroffen werden, woran wird sich gehalten? 
AdV oder NRW-OK?
BasisWMS/WFS für INSPIRE?

Abgabeformate: NAS, INSPIRE, SF (SimpleFeature), Modellkonform

NAS konforme Dienste geben komplexe Geometrien ab.
Vereinfachtes Schema und Modellkonform (AAA-komform) geben SimpleFeature ab.

> Während für WFS ausschließlich die Spezifikationen geprüft werden müssen 
> (hält sich der XtraServer an diese?), sind bei WMS noch die Belange der 
> Darstellung von Bedeutung. Welcher SK wird verwendet. Soll das Ziel die
>  bundesweit einheitliche Darstellung sein?  



# AdV-Festlegungen zum Web Feature Service (WFS)

Bereitstellung tagesaktueller Daten über das Internet
Spezifikationen für andere Dienste (Web Coverage Service WCS, ATOM-Feeds oder Geoservice REST API) werden bei Bedarf ausgearbeitet

__Motivationen:__
	* Aktuelle Daten bereit stellen
	* Bereitstellung in verschiedenen Formaten (nicht nur GML)
	* Zugriff auch für Nicht-GIS-Experten erleichtern
	* Senkung des Verwaltungsaufwandes

__AdV-Profil__ stellt allgemeine Festlegungen an WFS auf. Diese werden für die jeweiligen Produkte noch in __Produktspezifikationen__ genauer ausdifferenziert (AAA-WFS und Nicht-AAA-WFS)

__Grundsätze der Spezifizierung:__
	* Anforderungen und Bedürfnisse von Vermessungsverwaltungen und deren Kunden müssen berücksichtigt werden
	* Technische Fähigkeiten der Clients sind zu beachten
	* Zu Beachten ist, dass viele externe Nutzer oft einfacher strukturierte Daten erwarten.
	* Möglichst hohe Performanz ist angestrebt

__INSPIRE-Anforderungen__
	* Unterstützung Mehrsprachenanforderungen
	* Extended Capabilities validiert gegen XML-Schema im INSPIRE Schemarepository
	* Unterstürzung der WFS 2.0 Konformitätsklassen:
		- Simple WFS
		- HTTP GET
	* Unterstützung Filter Encoding 2.0 Konformitätsklasse:
		- Query
	* Unterstützung der Anforderungen Teil B und C
		- Basic WFS
		- Ad-hoc Query
		- ....s.u.
	* Für jede Produktspezifikation muss klargestellt sein ob sie in Punkt 2 oder Punkt 2 __und__ 3 INSPIRE-konform sein soll.
	* Dienst muss mind. die INSPIRE-Verpflichtungen hinsichtlich der Qualität erfüllen.

__AdV-WFS-Profil:__
	* Falls WFS 2.0: Basic WFS, HTTP GET
	* Empfehlung auch: Inheritance, HTTP POST
	* Rückgabe des kompletten Inhaltes unter Angabe einer BoundingBox und CRS
	* Verwendung der OGC-Schemata
	* Verwendung der AdV-Schemata
	* Für alle Objektarten die Lagekoordinaten als Raumbezug verwenden müssen diese CRS unterstützt werden:
		- Die in dem die Daten originär geführt werden (z.b. 25832, 25833)
		- ERTS geographisch (EPSG:4258)
	* Empfehlung: Falls ein korrespondierender WMS existiert, sollte dieser im selben CRS angeboten werden.


__AAA-WFS-Profil:__
	* Dienst muss alle Anforderungen des AdV-WFS-Profils erfüllen
	* Muss ausschließlich Objektversionen mit nicht abgeschlossenem Lebenszeitintervall bereitstellen
	* Identifikator
	* Keywords
		- Geobasisdaten
		- Art des Dienstes (WFS)
		- Datengrundlage (ATKIS)
		- langschriftlicher Name Datengrundlage
		- enthaltene Datenthemen
		- Ländercode
		- langschriftlicher Name des Landes
		- gewählte Schemavariante (z.b. AAA-Modell-basiert)

> Weitere Keywords werden in den Produktspezifikationen definiert. Von diesen 
> sind bisher die wenigsten realisiert.	

* Der Dienst muss als Titel den in der Produktspezifikation festgelegten Titel haben.
* Titel der im Identifikator festgelegt ist.
* Parameter AccessConstraints muss Nutzungsbedingungen aufführen.
* Empfohlen ist die Variante mit URL
* Wenn Nutzungsbedingungen existieren muss der zutreffende Wert aus MD_RestrictionCode gemäß ISO 19115:2003 angegeben werden.

http://www.geoportal.de/SharedDocs/Downloads/DE/GDI-DE/Architektur_GDI_DE-Konventionen_Metadaten.pdf

* Es soll mind. der bundeseinheitliche Grunddatenbestand bereitgestellt werden.


# AdV-ALKIS-WFS Produktspezifikation
~~Version 0.9, 22.04.2013~~

* Ebenfalls drei Datenaustauschmodelle
	- NAS-konform
	- AAA-Modell-konform
	- Vereinfachtes Ausstauschschema
		+ Dieses kann als INSPIRE-konformer Dienst genutzt werden
* Muss alle Anforderungen des AAA-WFS-Profil der AdV erfüllen
* Mind. OGC WFS Version 1.1.0 erfüllen
	- Um möglichst viele Nutzer und Clients unterstützen zu können
* GML-Version 3.2.1 verpflichtend
* INSPIRE-Anforderungen hinsichtlich Leistung, Kapazität und Verfügbarkeit
* INSPIRE schreibt WFS 2.0 vor, daher kann dieser Dienst nicht für die Bereitstellung von ALKIS-Daten für INSPIRE genutzt werden.
	- __Wieso wurde dann weiter oben das Vereinfachte Austauschschema als INSPIRE geeignet eingestuft. Das erfordert auch nur WFS 1.1.0__
* Eigentümerdaten unterliegen dem Datenschutz. Daher gibt es grundsätzlich zwei Benutzergruppen, für die jeweils Möglichkeiten zu schaffen sind
	- Behörden/Nutzer mit berechtigtem Interesse
	- Nutzer ohne berechtigtes Interesse
* Anforderungen an Element <Abstract>
* Anforderungen an Keywords
* 
	


# AdV-Produktspezifikation für ATKIS-DLM-WFS

WFS nach OGC Spezifikationen
__Grundlage AdV-WFS-Profil (Version 1.0.0)__
> Weitere Dienstarten sind nicht Gegenstand des Dokuments, sondern 
> gegebenenfalls künftig in weiteren Profilen auszuarbeiten.

AdV-Profile beschreiben allgemeine Festlegungen der Art der Datenbereitstellung.
Produktspezifikationen beschreiben Umfang und Art der Datenbereitstellung in Form von Produkten die unmittelbar verwendet werden können.

__Austauschschemata:__
* AAA-Modell-basiert
	- Inhaltlich und strukturell an NAS (AAA-Modell)
	- Anpassungen bei der Kodierung
	- Richtet sich an Experten die mit AAA vertraut sind
	- SimpleFeature
* NAS-konform
	- Richtet sich an AAA-Experten die mit Clients arbeiten die komplexe Objekt- und Geometriestrukturen verarbeiten können.
* Vereinfachtes Datenaustauschschema
	- vereinfachtes, inhaltlich und strukturell abweichendes Schema.
	- z.b. Fluren&Gemarkungen, flurstueckEigentuemer
	- vereinfachte Schemata die für bestimmte Datenabfragen aufbereitet wurden und dadurch einen wesentlichen Performancegewinn bringen.
	
__Nicht Gegenstand der Spezifikationen:__
	* Zugriffsrechte
	* Abrechnungsmodelle
	* Absicherung der Dienste

__Anforderungen:__
	* ATKIS-DLM-WFS muss alle Anforderungen des AAA-WFS-Profils Version 1.0.0 der AdV erfüllen
	* Liefert mind. die Objekt-, Attribut- und Relationsarten des Grundbestandes GeoInfoDok
	* Qualitätskriterien (Leistung, Kapazität, Verfügbarkeit) entsprechend der INSPIRE-Bestimmungen.
	* Muss Version 1.1 des _OGC-WFS Standards_ unterstützen (Sinnvollerweise auch Version 2.0)
	* Wenn WFS 2.0 - Konformitätsklassen:
		- Basic WFS
		- Inheritance
		- HTTP GET
		- HTTP POST (Empfehlung)
    * Wenn WFS 2.0 - Gemäß _OGC Filter Encoding_ folgende Konformitätsklassen:
    	- Query
    	- Ad-hoc-Query
    	- ResourceIdentifikation
    	- Minimum Spatial Filter
    	- Minimum Standard Filter
    	- Minimum XPath
    	- Minimum Temporal Filter
    * Wenn WFS 2.0 - Vorgeschriebene StoredQuery:
    	- __AlleObjekt__ anhand einer beschreibenden __BoundingBox__ und des __CRS__
    	- Weitere StoredQueries sind nicht gefordert
    	- Unter Absprache mit den Nutzern können weitere festgelegt werden.
    * Unterstützt werden ERTS89 UTM 32 (EPSG:25832) und UTM 33 (EPSG:25833) 
    * Um INSPIRE konform zu sein, muss es den Anforderungen eines entsprechenden Download-Services entsprechen. 
    
__Festlegungen für Schemavariante AAA-Modell-basiert__
	* Dienst muss der Schemavariante AAA-WFS-Profil entsprechen und gegen NAS-XSD-Schema valide sein.
	* Muss im Capabilities-Element einen Identifikator enthalten der den Namenskonventionen entspricht (`WFS_{Ländercode}_ATKIS-{DLM}_AAA-Modell-basiert`)
	* Mehrere weitere Keywords müssen enthalten sein.
	* Capabilities muss im Titel den Identifikatior (s.o.) haben.
	* Muss bestimmten Text im Abstract haben.

__Festlegung für optionale Schemavariante NAS-konform__
	* Muss der Schemavariante NAS-konform aus AAA-WFS-Profil entsprechen und NAS-XSD-Schema valide sein.
	* Identifikator
	* Keywords
	* Abstract

__WFS-G (Web Feature Service Gazetteer, Version 2.0)__
Dies ist ein Dienst mit erweiterten Suchfunktionen 
Unscharfe Suche (unterschiedliche Schreibweisen von Namen, Sonderzeichen ersetzen, Case Insensitive, Führende Namenszusätze kürzen, Abkürzungen)
Phonetische Suche mit SoundEx



__Verfügbare bzw. zu implementierende Dienste__
* ATKIS Basis-DLM
	- sf (SimpleFeature)
	- nas
	- gcl (GeoChangeLog)
	- ins-dl (INSPIRE Download Service)
	- ins-view (WMS, INSPIRE View Service)
	- _gsfs (Geoservice REST API, optionaler Service)_
* ATKIS DLM50
	- die gleichen wie oben
* WebAtlas (WMS, webatlas)
* WebAtlas dynamisch (WMS, webatlas-dyn)
* Fluren+Gemarkungen (flur/wfs, flur/wms)


__Qualität nach INSPIRE-Kriterien__
Leistung: 		Antwort nach max. 30 Sekunden, 500 Features pro Sekunde
Kapazität: 		Höchstmenge gleichzeitiger Abfragen. Pro Sekunde mind. 10. Zahl
				der gleichzeitigen Abfragen kann auf 50 beschränkt werden.
Verfügbarkeit: 	Soll 99% betragen, d.h. Ausfallzeit im Jahr max. 87,6 Stunden


__WFS Dienst testen:__
http://cite.opengeospatial.org/teamengine/

GDI-DE Testsuite um INSPIRE Konformität zu prüfen:
https://testsuite.gdi-de.org/gdi/

Capabilities-Viewer:
https://geoportal.bayern.de/getcapabilities/
