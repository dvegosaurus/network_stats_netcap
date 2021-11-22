# network stats with netcap

## URI

Kibana:
http://<dockerhost>:5601
Grafana:
http://<dockerhost>:3000

## Docker
- Grafana
    - Included
- InfluxDB 1.8
    - Included
- Prometheus
    - Todo
- dreadl0ck/netcap:alpine-v0.5
    - Included
- elasticsearch
    - Included
- kibana
    - Included
- logstash
    - Included

## setup
- Run create-folder.sh
- Run docker compose
- install packetbeat
    - add the config file

Netcap and telegraf are attached to the host network to allow testing with port mirroring.

### ElasticSearch config
ElasticSearch need some config to work with packetbeat. Kibana will handle this for us :

- install packetbeat
- run "packetbeat setup -e"

This will also create some basic Packetbeat dashboard

## Grafana 
Datasources for netcap data ans packetbeat data are provisionned.

