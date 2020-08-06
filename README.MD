# CeNTREX Monitoring
Spins up a Docker instance of the  CeNTREX monitoring stack

Default init commands for influxDB are located in influx_init.iql.   
These are only executed when no databases exist yet, so in order to add things to an existing container the following command needs to be run:  
`docker-compose exec influxdb /usr/bin/influx -import -path /docker-entrypoint-initdb.d/influx_init.iql`  

Grafana datasources are added to the `./grafana-provisioning/datasources/` folder as `.yml` files.

The data can be stored either in docker volumes, or by mapping to a local folder. Both options are present in the compose file, with one of either having to be commented out.

Create the instance by `running docker-compose up -d`.  
Start the instance with `docker-compose start`.  
Stop the instance with `docker-compose stop`.  
Remove the instance with `docker-compose down`.  
Remove all unused volumes with `docker volume prune`.
