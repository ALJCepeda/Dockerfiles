FROM literphor/basedebian:latest
MAINTAINER Literphor

LABEL Version="1.0"


RUN wget -O fpc.tar http://sourceforge.net/projects/freepascal/files/Linux/2.6.4/fpc-2.6.4.i386-linux.tar/download
RUN mkdir fpc
RUN tar -xvf fpc.tar -C fpc --strip-components 1
RUN cd fpc && printf '/usr\nn\ny\ny\nn\nn' | /fpc/install.sh
RUN cd / && rm -rf fpc*