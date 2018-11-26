
FROM ubuntu:16.04

RUN apt-get update && apt-get -y install python python-pip git nginx librrd-dev
RUN pip install flask flask-JWT lxml rrdtool

RUN useradd drop-core

RUN git clone https://github.com/droopp/webbone.git /home/drop-core/
RUN rm -rf /etc/nginx/conf.d/*
RUN rm -rf /home/drop-core/.git

RUN chown -R drop-core:drop-core /home/drop-core/*

COPY ./nginx.conf /etc/nginx/
COPY ./webbone.conf /etc/nginx/conf.d/
COPY ./start /home/drop-core/
