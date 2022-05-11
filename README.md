# Modellierung von Verkehrsstärken mit GPS-Daten

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
3. `muenster_DTV_modelling.ipynb`
4. `muenster_traffic_density_estimation.ipynb`
