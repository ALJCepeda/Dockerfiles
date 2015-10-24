FROM literphor/basedebian:latest
MAINTAINER Literphor

LABEL Version="1.0"

RUN printf '%s\n%s\n' \
	'deb http://packages.dotdeb.org wheezy-php55 all' \
	'deb-src http://packages.dotdeb.org wheezy-php55 all' \
	| tee -a /etc/apt/sources.list
RUN wget http://www.dotdeb.org/dotdeb.gpg
RUN apt-key add dotdeb.gpg
RUN apt-get update	
RUN apt-get -y install php5-cli
RUN sed -i "s/error_reporting = .*/error_reporting = E_ALL/" /etc/php5/cli/php.ini
RUN sed -i "s/display_errors = .*/display_errors = On/" /etc/php5/cli/php.ini