# Modellierung von Verkehrsstärken mit GPS-Daten

## Inhalte des Repositories

## Datenquellen

## Installation und Ausführung der Modelle
Zur Installation der Modelle sind folgende Schritte erforderlich:
1. [Conda](https://docs.conda.io/en/latest/) installieren
2. Dieses Repository klonen
3. In der Kommandozeile in das lokale Verzeichnis des Repositorys wechseln
4. Ausführen von `conda env create` (erzeugt die in `environment.yml` definierte Umgebung `verkehrsstaerke-gps`)
5. Ausführen von `conda activate verkehrsstaerke-gps`

Die Modelle sollten in der folgenden Reihenfolge aufgerufen werden, da die Ausgangsdaten eines Modells als Eingangsdaten für das jeweils folgende Modell verwendet werden:
1. `envirocar_get_data.ipynb`
2. `envirocar_muenster_exploration.ipynb`
4. `muenster_traffic_density_estimation.ipynb`
5. `muenster_DTV_modelling.ipynb`

## Urheber*innen
Christina Vergara Ossenberg, János Sebestyén (beide Wuppertal Institut für Klima, Umwelt, Energie gGmbH)

## Lizenz
Sämtliche Inhalte des Repositories stehen unter der Creative Commmons Namensnennung 3.0 Deutschland (CC BY 3.0 DE) Lizenz. Sie können geteilt und weiterverarbeitet werden, wenn dabei auf die Urheber*innen und die Lizenz verwiesen wird und eventuelle Änderungen kenntlich gemacht werden. Die vollständige Lizenz kann unter folgendem Link eingesehen werden: https://creativecommons.org/licenses/by/3.0/de/

Die von den hier veröffentlichten Modellen verwendeten Datenquellen stehen unter eigenen Lizenzen, siehe oben.

Jahr der Veröffentlichung: 2022
