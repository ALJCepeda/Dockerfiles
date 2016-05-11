FROM aljcepeda/debian:latest
MAINTAINER aljcepeda

LABEL Version="1.0"

RUN printf '%s\n%s\n' \
	'deb http://packages.dotdeb.org squeeze-php54 all' \
	'deb-src http://packages.dotdeb.org squeeze-php54 all' \
	| tee -a /etc/apt/sources.list
RUN wget http://www.dotdeb.org/dotdeb.gpg
RUN apt-key add dotdeb.gpg
RUN apt-get update
RUN apt-get -y install php5-cli
