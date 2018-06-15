# Humanities Workbench with Elasticsearch

A Docker Compose stack that provides elasticsearch  and a Jupyter notebook (based on britishlibrarylabs/humanitiesworkbench) to load metadata into it and search it. It comes with a demonstration notebook which steps through getting some metadata (in this case, some information about books scanned by the Microsoft Books Project at the British Library), adding it to an elasticsearch index and then running some basic queries on it.

## Purpose

While this could have been set up to have an elasticsearch service with the index already in the image, it is more useful to see how that index was created. The included notebook steps through the basics of getting some data represented in JSON, putting it into Elasticsearch using the bulk ingest API and the elasticsearch-py "helper" method, and finally running some basic searches on the data.

There is far more that can be done with elasticsearch, including being specific with how it analyses the values, Query DSL, highlights and so on. This stack provides an environment that has many tools for textual analysis and visualisations, as well as an elasticsearch service. 

## Usage

First, you need to have docker and docker compose installed on whatever system you want to run this on. Then, the stack can be instantiated in the usual way:

    $ docker compose up -d --build

The jupyter notebook service is based on the Jupyter Docker Stack, and uses a token login. This token can be found in the docker logs when you start this service up. You can retrieve these on the commandline in the following way:

    $ docker logs frontend