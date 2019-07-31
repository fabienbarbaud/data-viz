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

# Quelle représentation graphique ?

![](images/choisir-nom-entreprise.jpg)

---

# Quelle représentation graphique ?

[The Data Visualisation Catalogue](https://datavizcatalogue.com/search.html)

---

# Composer un dashboard

![](images/dashboard-wireframe.png)

---

# Composer un dashboard

## Les règles à suivre 

- Se fixer un objectif et un seul
- Connaître son public/l'avoir identifié
- Raconter une histoire
- Adapter les couleurs au contexte
- Rester simple

---

# Composer un dashboard

## Par la pratique 

### Les prix des carburants

Réaliser une maquette papier d'un dashboard sur les prix des carburants en France.

Identifier le public cible et en quoi votre dashboard lui apporte un intérêt.

Données sources : https://www.prix-carburants.gouv.fr/rubrique/opendata/

---

# Les outils

![](images/boite-a-outils-entrepreneurs.jpg)

---

# Les outils

## Microsoft

![](images/power-bi-logo.jpg)

---

# Les outils

## Google

![](images/google-data-studio-logo.png)

---

# Les outils

## Tableau Software

![](images/tableau-logo.jpg)

---

# Travaux pratique

## Elasticsearch et Kibana

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

---

# Travaux pratique

## Elasticsearch : chargement de la donnée

```text
$ docker exec -it elastic bash
[root@f5fa51111c81 elasticsearch]# curl -OL \
https://github.com/fabienbarbaud/data-viz/raw/master/data/accounts.json
[root@f5fa51111c81 elasticsearch]# curl -u elastic \
-H 'Content-Type: application/x-ndjson' \
-XPOST 'localhost:9200/bank/account/_bulk?pretty' \
--data-binary @accounts.json
```

Mot de passe : changeme
[Tutorial Elastic](https://www.elastic.co/guide/en/kibana/current/tutorial-build-dashboard.html)
