FROM ubuntu:20.04
LABEL maintainer="Test <test@liferay.com>"
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && \
    apt install net-tools && \
    apt-get update && \
    apt-get -y -q install \
        libreoffice \
        libreoffice-writer \
        ure \
        libreoffice-java-common \
        libreoffice-core \
        libreoffice-common \
        openjdk-11-jre \
        fonts-opensymbol \
        hyphen-en-us \
        fonts-dejavu \
        fonts-dejavu-core \
        fonts-dejavu-extra \
        fonts-droid-fallback \
        fonts-dustin \
        fonts-f500 \
        fonts-fanwood \
        fonts-freefont-ttf \
        fonts-liberation \
        fonts-lmodern \
        fonts-lyx \
        fonts-sil-gentium \
        fonts-texgyre \
        fonts-tlwg-purisa && \
    apt-get -y -q remove libreoffice-gnome && \
    rm -rf /var/lib/apt/lists/*
RUN adduser --home=/opt/libreoffice --disabled-password --gecos "" --shell=/bin/bash libreoffice
EXPOSE 8100
CMD /usr/bin/libreoffice --headless --nofirststartwizard  --nologo --accept="socket,host=0.0.0.0,port=8100;urp"
