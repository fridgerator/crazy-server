FROM phusion/baseimage
MAINTAINER nick franken <shnick@gmail.com>

RUN apt-get -q update && \
    apt-get -qy dist-upgrade && \
    apt-get install -qy libcurl4-openssl-dev bzip2 wget && \
    wget -q https://github.com/Jackett/Jackett/releases/download/v0.7.290/Jackett.Binaries.Mono.tar.gz /tmp && \
    tar -xvf /tmp/Jackett* && \
    mkdir /opt/jackett && \
    mv /tmp/Jackett/* /opt/jackett && \
    chown -R root:root /opt/jackett && \
    apt-get -y autoremove && \
    apt-get -y clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /tmp/*

ADD ./start.sh /start.sh

CMD ["./start.sh"]