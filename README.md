# Ultra kort intro

Alt du skal bruge er Docker og Docker-compose.

Klon projektet til en ønsket mappe.

`cd grafana-influxdb`

For at sætte en smule sikkerhed i setuppet, laver vi en lokal konfigurationsfil. Her kan du holde eventuelle passwords, installerede plugins mv. for dig selv. Vær dog opmærksom på, at du bliver bedt om at lave et nyt password første gang du logger på Grafana. Du kan derfor blot lade bruger og password forblive admin/admin.

`cp configuration.env .ENV`

`docker-compose up`

Hvis du vil have applikationerne til at køre som deamon, skal du blot tilføje et -d:

`docker-compose up -d`

I din browser åbner du http://ip-dresse:3000

Har du brug for et ekstra plugin? Intet problem.

Find det ønskede plugin på grafana.com/plugins - f.eks Alarm Box. Under installation finder du navnet på det ønskede plugin. I vores tilfælde skal kopiere 'btplc-alarm-box-panel'. Dette sætter du ind i din .ENV fil således:

GF_INSTALL_PLUGINS=grafana-clock-panel,grafana-worldmap-panel,grafana-piechart-panel,btplc-alarm-box-panel

Kør følgende:

`docker-compose down`

`docker-compose build`

`docker-compose up`

Nu skulle du gerne have det nye plugin tilgægeligt i dit setup:-)

This repository as an updated version of https://github.com/BushnevYuri/DockerGrafanaInfluxKit
