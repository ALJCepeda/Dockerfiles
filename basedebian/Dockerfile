FROM debian:wheezy
MAINTAINER Literphor

LABEL Version="1.0"

ENV DEBIAN_FRONTEND=noninteractive

ADD http://http.debian.net/debian/project/trace/ftp-master.debian.org /etc/trace_ftp-master.debian.org
ADD http://security.debian.org/project/trace/security-master.debian.org /etc/trace_security-master.debian.org

RUN gpg --keyserver 213.133.103.71 --recv-key 89DF5277 >/dev/null 2>&1
RUN gpg -a --export 89DF5277 | apt-key add -
RUN apt-get update

RUN printf '%s\n%s\n' \
	'deb http://packages.dotdeb.org wheezy all' \
	'deb-src http://packages.dotdeb.org wheezy all' \
	| tee -a /etc/apt/sources.list 

RUN apt-get update && apt-get -y dist-upgrade && apt-get -y autoremove && apt-get clean
RUN apt-get -y install apt-utils binutils dialog wget less curl vim