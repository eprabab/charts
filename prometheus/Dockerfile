FROM ubuntu

RUN apt-get update 

RUN apt -y install wget curl vim

RUN curl -s https://api.github.com/repos/prometheus/prometheus/releases/latest | grep browser_download_url | grep linux-amd64 | cut -d '"' -f 4 | wget -qi -

RUN tar -xvf prometheus*.tar.gz

COPY prometheus.yml ./

ENTRYPOINT ["/bin/sh","-c","/prometheus-*/prometheus","--config.file=/prometheus.yml"]
