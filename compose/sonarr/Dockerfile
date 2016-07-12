FROM phusion/baseimage
MAINTAINER nick franken <shnick@gmail.com>

RUN apt-get -q update && \
    apt-get -qy dist-upgrade && \
    apt-get install -qy apt-transport-https && \
    apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF && \
    echo "deb http://download.mono-project.com/repo/debian wheezy main" > /etc/apt/sources.list.d/mono-xamarin.list && \
    apt-key adv --keyserver keyserver.ubuntu.com --recv-keys FDA5DFFC && \
    echo "deb https://apt.sonarr.tv/ master main" > /etc/apt/sources.list.d/sonarr.list && \
    apt-get -q update && \
    apt-get install -qy nzbdrone && \
    rm /etc/apt/sources.list.d/sonarr.list && \
    chown -R root:root /opt/NzbDrone && \
    apt-get -y autoremove && \
    apt-get -y clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /tmp/*

ADD ./start.sh /start.sh

CMD ["./start.sh"]