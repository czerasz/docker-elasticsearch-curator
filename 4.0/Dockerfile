FROM debian:jessie

ARG ELASTICSEARCH_CURATOR_VERSION

RUN set -x &&\
    apt-get update &&\
    apt-get install -y wget &&\
    wget -qO - https://packages.elastic.co/GPG-KEY-elasticsearch | apt-key add - &&\
    echo 'deb http://packages.elastic.co/curator/4/debian stable main' > /etc/apt/sources.list.d/curator.list &&\
    apt-get update &&\
    apt-get install -y python-elasticsearch-curator=$ELASTICSEARCH_CURATOR_VERSION &&\
    apt-get remove -y wget &&\
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["/usr/local/bin/curator"]
