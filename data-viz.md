<!-- page_number: true -->
<!-- footer: Data Visualisation : les principes -->

Data Visualisation : les principes
===

![](images/data-visualization-660x330.jpg)

##### Comment présenter sa données

###### par [Fabien Barbaud](fabien.barbaud@timeonegroup.com) - [@BarbaudFabien](https://twitter.com/BarbaudFabien)

---

# Définition

La visualisation des données est un ensemble de méthodes de **représentation graphique**, en deux ou trois dimensions, utilisant ou non de la couleur et des trames. Les moyens informatiques permettent de représenter des **ensembles complexes de données**, de manière plus **simple, didactique et pédagogique**.

[Wikipedia](https://fr.wikipedia.org/wiki/Visualisation_de_donn%C3%A9es)

---

# Travaux pratique

## Elastisearch et Kibana

```text
$ docker pull \
docker.elastic.co/elasticsearch/elasticsearch:7.3.0
$ docker pull docker.elastic.co/kibana/kibana:7.3.0
$ docker run -d -p 9200:9200 --name=elastic \
-e "http.host=0.0.0.0" -e "transport.host=127.0.0.1" \
docker.elastic.co/elasticsearch/elasticsearch:7.3.0
$ docker run -d -p 5601:5601 --link elastic:elasticsearch \
docker.elastic.co/kibana/kibana:7.3.0
```

http://localhost:5601
