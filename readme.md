# network stats with netcap

Docker setup to test network monitoring with Grafana. Several setup with different capture method and databases are used :
- netcap to InfluxDB | OK
- netcap to Prometheus | todo
- Packetbeat to ElasticSearch | OK
    - with Kibana and logstash
- Wireshark to Elasticsearch | todo

Some setup with Graylog and or Loki might be interesting to try.

##  Sources 

netcap setup : https://docs.netcap.io/metrics
wireshark / filebeat setup : https://www.elastic.co/fr/blog/analyzing-network-packets-with-wireshark-elasticsearch-and-kibana

## URIS

Kibana:
http://dockerhost:5601

Grafana:
http://dockerhost:3000

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
Packetbeat is not included and needs to installed on a client

### ElasticSearch config
ElasticSearch need some config to work with packetbeat. Kibana will handle this for us :

- install packetbeat
- run "packetbeat setup -e"

This will also create some basic Packetbeat dashboard

## Grafana 
Datasources for netcap data ans packetbeat data are provisionned.

