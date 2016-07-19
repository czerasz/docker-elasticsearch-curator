# About this Repo

This is the Git repo for [elasticsearch curator](https://hub.docker.com/r/czerasz/docker-elasticsearch-curator/). See [the Docker Hub page](https://hub.docker.com/r/czerasz/docker-elasticsearch-curator/) for the full readme on how to use this Docker image and for information regarding contributing and issues.

## How to use this image

You can run the default `elasticsearch-curator` command simply:

```
$ docker run -it --rm --name=elasticsearch-curator czerasz/docker-elasticsearch-curator:4.0 --version
```

Use a custom configuration file:

```
$ docker run -it --rm \
             --name=elasticsearch-curator \
             --volume=$PWD/configuration/:/etc/elasticsearch/curator/:ro \
             czerasz/docker-elasticsearch-curator:4.0 --config /etc/elasticsearch/curator/config.yml
```

Connect to an existing Elasticsearch node running inside a Docker container:

```
$ docker run -it --rm \
             --name=elasticsearch-curator \
             --volume=$PWD/configuration/:/etc/elasticsearch/curator/:ro \
             --link=elasticsearch:elasticsearch \
             czerasz/docker-elasticsearch-curator:4.0 --config /etc/elasticsearch/curator/config.yml /etc/elasticsearch/curator/actions.yml

```

Run bash inside, using this image:

```
$ docker run -it --rm \
             --name=elasticsearch-curator \
             --volume=$PWD/configuration/:/etc/elasticsearch/curator/:ro \
             --link=elasticsearch:elasticsearch \
             --entrypoint=/bin/bash \
             czerasz/docker-elasticsearch-curator:4.0
```
