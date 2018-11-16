
FROM ubuntu:16.04

RUN apt-get update && apt-get -y install python python-pip git nginx
RUN pip install flask flask-JWT lxml

RUN useradd drop-core

RUN git clone https://github.com/droopp/webbone.git /home/drop-core/
RUN rm -rf /etc/nginx/conf.d/*

COPY ./nginx.conf /etc/nginx/
COPY ./webbone.conf /etc/nginx/conf.d/
COPY ./start /home/drop-core/
