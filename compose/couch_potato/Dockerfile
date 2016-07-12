FROM phusion/baseimage
MAINTAINER nick franken <shnick@gmail.com>

RUN apt-get -q update && \
    apt-get -qy dist-upgrade && \
    apt-get install -qy \
        git-core \
        libffi-dev \
        libssl-dev \
        zlib1g-dev \
        libxslt1-dev \
        libxml2-dev \
        python \
        python-pip \
        python-dev \
        build-essential \
    && \
    pip install lxml cryptography pyopenssl && \
    git clone https://github.com/RuudBurger/CouchPotatoServer /opt/couchpotato && \
    ls -alch /opt/couchpotato && \
    chown -R root:root /opt/couchpotato && \
    apt-get -y autoremove && \
    apt-get -y clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /tmp/*

ADD ./start.sh /start.sh

CMD ["./start.sh"]