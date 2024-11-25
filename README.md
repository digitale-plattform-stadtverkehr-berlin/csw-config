# Konfigurationsdaten für pyCSW

Das Repository enthält eine Konfigurationsdatei und Initialisierungsdaten für eine [pyCSW-Instanz](https://pycsw.org/).

Die Dateien enthalten Daten für die LayerInfos im Masterportal auf https://viz.berlin.de. 

## Hinzufügen von Datensätzen

Neue Datensätze müssen als XML-Datei auf Basis des Templates csw_template.xml bereitgestellt werden.
Erforderlich sind
* Die Datensatz-ID, die in der Masterportal Konfiguration angegeben wird. Diese wird einmal als ```fileIdentifier``` und einmal als Attribut ```id``` im Element ```MD_DataIdentification```.
* Der Titel als ```title```.
* Der Beschreibungstext als ```abstract```. Wenn in der Beschreibung HTML-Formatierungen verwendet werden sollen müssen diese HTML-Encoded werden.



### Import der Daten in pycsw:
```
> docker compose exec csw pycsw-admin.py -f /home/pycsw/pycsw.cfg -c load_records -p /home/pycsw/init-data -y
```
