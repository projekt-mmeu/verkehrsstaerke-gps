# Modellierung von Verkehrsstärken mit GPS-Daten
In diesem Repository befinden sich die Ergebnisse einer Modellierung von Verkehrsstärken mit GPS-Daten, die im Rahmen des Projektes mMEU - Mobilitätsbedingte Mikroplastikemissionen in der Umwelt durchgefüht wurde. Das Projekt wurde vom Bundesministerium für Digitales und Verkehr als Teil der Innovationsinitiative mFUND gefördert. Link zur Projektwebsite: https://projekt-mmeu.de/

Zur Modellierung der Verkehrsstärken werden automobile Fahrdaten der Citizen Science Plattform [enviroCar](https://envirocar.org/?lng=de) ausgewertet. Durch lineare Regression auf automatische Zähldaten der Stadt Münster (bezogen von [CODEformuenster](https://traffics.codeformuenster.org/)) wird eine Schätzung für die durchschnittliche tägliche Verkehrsstärke (DTV) je Straßenabschnitt vorgenommen. Die Modellergebnisse werden als Shapfile (.shp) ausgegeben.

## Modelldateien
* `enviroCar_get_data.ipynb`
In diesem File werden Daten von der Envirocar-Schnittstelle heruntergeladen und gespeichert.
* `envirocar_muenster_exploration.ipynb`
In diesem File wird ein zuvor gespeicherter Datensatz für Münster explorativ untersucht, vor allem bezüglich seiner zeitlichen und räumlichen Auflösung und Abdeckung.
* `muenster_traffic_density_estimation.ipynb`
 In diesem File wird aus dem oben genannten Datensatz ein Maß für die Verkehrsdichte abgeleitet, indem die Track-Punkte den jeweiligen Straßenabschnitten zugeordnet werden.
* `muenster_DTV_modelling.ipynb`
In diesem File wird die abgeleitete Verkehrsdichte genutzt, um verschiedene Modelle zur Schätzung der DTV zu erproben. Dazu werden Zähldaten von CODEforMünster verwendet.
* `environment.yml`
In dieser Umgebungs-Datei werden für die Ausführung der Modelle benötigte Pakete spezifiziert.

## Datenquellen
Die folgenden Datenquellen werden für die Modellierung verwendet:
* Automobile Fahrdaten der Citizen Science Plattform [enviroCar](https://envirocar.org/?lng=de). Diese stehen unter der Open Database License (ODbL), die hier abgerufen werden kann: https://opendatacommons.org/licenses/odbl/1-0/. Die Daten werden beim Ausführen des Modells über das Python-Paket [enviroCar-py](https://github.com/enviroCar/envirocar-py) automatisch heruntergeladen und in `/data/envirocar_muenster/` gespeichert. Sie sind nicht Bestandteil dieses Repositories.
* Kfz-Zähldaten von automatischen Zählstellen der Stadt Münster. Sie stehen unter der Datenlizenz Deutschland – Namensnennung – Version 2.0, die hier beschrieben ist: https://www.govdata.de/dl-de/by-2-0. Die Daten wurden von [CODEformuenster](https://traffics.codeformuenster.org/) manuell für jede der zehn Zählstellen ausgelesen und zur CSV-Datei `/data/dtv_muenster.csv` zusammengefasst.
* Kartengrundlage von [OpenStreetMap](https://www.openstreetmap.org/) zum Verlauf von Straßenabschnitten. Die Daten stehen unter der Open Database License (ODbL), die hier abgerufen werden kann: https://opendatacommons.org/licenses/odbl/. Heruntergeladen wurden die Daten vom [Geofabrik Download Server](https://download.geofabrik.de/europe/germany/nordrhein-westfalen/muenster-regbez.html) als Karten-Kachel unter der Lizenz CC BY-SA 2.0 (https://creativecommons.org/licenses/by-sa/2.0/). © Geofabrik GmbH und OpenStreetMap-Mitwirkende. Sie befinden sich im Ordner `/data/OSM_muenster`

## Installation und Ausführung der Modelle
Um die Modelle auszuführen, ist eine Installation von Conda und der bereitgestellten Umgebung (environment.yml) empfehlenswert, da so alle erforderlichen Pakete und deren Abhängigkeiten installiert werden. Dazu sind folgende Schritte auszuführen:
1. [Conda](https://docs.conda.io/en/latest/) installieren
2. Dieses Repository klonen
3. In der Kommandozeile in das lokale Verzeichnis des Repositorys wechseln
4. Ausführen von `conda env create` (erzeugt die in `environment.yml` definierte Umgebung `verkehrsstaerke-gps`)
5. Ausführen von `conda activate verkehrsstaerke-gps`

Die Modelle sollten in der unter "Modelldateien" angegebenen Reihenfolge aufgerufen werden, da die Ausgangsdaten eines Modells als Eingangsdaten für die jeweils folgenden Modelle verwendet werden.

## Urheber*innen der Modelldateien
Christina Vergara Ossenberg, János Sebestyén (beide Wuppertal Institut für Klima, Umwelt, Energie gGmbH)

## Lizenz
Die oben aufgeführten Modelldateien und diese Dokumentation (README.md) stehen unter der Creative Commmons Namensnennung 3.0 Deutschland (CC BY 3.0 DE) Lizenz. Sie können geteilt und weiterverarbeitet werden, wenn dabei auf die Urheber*innen und die Lizenz verwiesen wird und eventuelle Änderungen kenntlich gemacht werden. Die vollständige Lizenz kann unter folgendem Link eingesehen werden: https://creativecommons.org/licenses/by/3.0/de/

Die von den hier veröffentlichten Modellen verwendeten Datenquellen stehen unter eigenen Lizenzen, siehe unter "Datenquellen".

Jahr der Veröffentlichung: 2022
