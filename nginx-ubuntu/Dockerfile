FROM ubuntu:14.04

MAINTAINER Bruno Orlandi, brorlandi@gmail.com


RUN echo "deb http://ppa.launchpad.net/nginx/stable/ubuntu trusty main" >> /etc/apt/sources.list
RUN echo "deb-src http://ppa.launchpad.net/nginx/stable/ubuntu trusty main" >> /etc/apt/sources.list
RUN apt-get update

RUN apt-get install -y vim net-tools

RUN apt-get install -y nginx

RUN rm -v /etc/nginx/nginx.conf
ADD nginx.conf /etc/nginx/

EXPOSE 80

RUN echo "daemon off;" >> /etc/nginx/nginx.conf
CMD service nginx start
