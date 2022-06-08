# Modellierung von Verkehrsstärken mit GPS-Daten
In diesem Repository befindet sich die vollständige Dokumentation der Modellierung von Verkehrsstärken mit GPS-Daten, die im Rahmen des Projektes mMEU - Mobilitätsbedingte Mikroplastikemissionen in der Umwelt durchgefüht wurde. Das Projekt wurde vom Bundesministerium für Digitales und Verkehr als Teil der Innovationsinitiative mFUND gefördert. Link zur Projektwebsite: https://projekt-mmeu.de/

Zur Modellierung der Verkehrsstärken werden automobile Fahrdaten der Citizen Science Plattform [enviroCar](https://envirocar.org/?lng=de) ausgewertet. Durch lineare Regression auf automatische Zähldaten der Stadt Münster (bezogen von [CODEformuenster](https://traffics.codeformuenster.org/)) wird eine Schätzung für die durchschnittliche tägliche Verkehrsstärke (DTV) je Straßenabschnitt vorgenommen. Die Modellergebnisse werden als Shapfile (.shp) ausgegeben.

## Modelldateien
* `enviroCar_get_data.ipynb`
In diesem File werden Daten von der Envirocar-Schnittstelle heruntergeladen und in `/data` gespeichert.
* `envirocar_muenster_exploration.ipynb`
In diesem File wird ein zuvor gespeicherter Datensatz für Münster explorativ untersucht, vor allem bezüglich seiner zeitlichen und räumlichen Auflösung und Abdeckung.
* `muenster_traffic_density_estimation.ipynb`
 In diesem File wird aus dem oben genannten Datensatz ein Maß für die Verkehrsdichte abgeleitet, indem die Track-Punkte den jeweiligen Straßenabschnitten zugeordnet werden.
* `muenster_DTV_modelling.ipynb`
In diesem File wird die abgeleitete Verkehrsdichte genutzt, um verschiedene Modelle zur Schätzung der DTV zu erproben. Dazu werden Zähldaten von CODEforMünster verwendet.

## Datenquellen

## Installation und Ausführung der Modelle
Um die Modelle auszuführen, ist eine Installation von Conda und der hier verfügbaren Umgebung (environment.yml) empfehlenswert, da so alle erforderlichen Pakete und deren Abhängigkeiten installiert werden. Dazu sind folgende Schritte auszuführen:
1. [Conda](https://docs.conda.io/en/latest/) installieren
2. Dieses Repository klonen
3. In der Kommandozeile in das lokale Verzeichnis des Repositorys wechseln
4. Ausführen von `conda env create` (erzeugt die in `environment.yml` definierte Umgebung `verkehrsstaerke-gps`)
5. Ausführen von `conda activate verkehrsstaerke-gps`

Die Modelle sollten in der unter "Modelldateien" angegebenen Reihenfolge aufgerufen werden, da die Ausgangsdaten eines Modells als Eingangsdaten für die jeweils folgenden Modelle verwendet werden.

## Urheber*innen der Modelldateien
Christina Vergara Ossenberg, János Sebestyén (beide Wuppertal Institut für Klima, Umwelt, Energie gGmbH)

## Lizenz
Die oben aufgeführten Modelldateien stehen unter der Creative Commmons Namensnennung 3.0 Deutschland (CC BY 3.0 DE) Lizenz. Sie können geteilt und weiterverarbeitet werden, wenn dabei auf die Urheber*innen und die Lizenz verwiesen wird und eventuelle Änderungen kenntlich gemacht werden. Die vollständige Lizenz kann unter folgendem Link eingesehen werden: https://creativecommons.org/licenses/by/3.0/de/

Die von den hier veröffentlichten Modellen verwendeten Datenquellen stehen unter eigenen Lizenzen, siehe unter "Datenquellen".

Jahr der Veröffentlichung: 2022
