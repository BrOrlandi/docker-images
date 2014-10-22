FROM ubuntu:14.04

MAINTAINER Bruno Orlandi, brorlandi@gmail.com

RUN apt-get update
RUN apt-get install -y wget vim net-tools

WORKDIR home/
RUN wget http://nginx.org/keys/nginx_signing.key
RUN apt-key add nginx_signing.key

RUN echo "deb http://ppa.launchpad.net/nginx/stable/ubuntu trusty main" >> /etc/apt/sources.list
RUN echo "deb-src http://ppa.launchpad.net/nginx/stable/ubuntu trusty main" >> /etc/apt/sources.list
RUN apt-get update


RUN apt-get install -y nginx

RUN rm -v /etc/nginx/nginx.conf
ADD nginx.conf /etc/nginx/

EXPOSE 80

RUN echo "daemon off;" >> /etc/nginx/nginx.conf
CMD service nginx start
