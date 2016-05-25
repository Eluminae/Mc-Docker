FROM phusion/baseimage

#...put your own build instructions here....#

RUN apt-get update

RUN apt-get install -y wget unzip software-properties-common

RUN add-apt-repository ppa:webupd8team/java
RUN apt-get update
RUN yes | apt-get install oracle-java8-installer

RUN wget https://bitbucket.org/wisemapping/wisemapping-open-source/downloads/wisemapping-v4.0.3.zip -O /root/wisemapping.zip
RUN unzip /root/wisemapping.zip -d /home/
RUN rm /root/wisemapping.zip

#...........................................#

#...put your own services here..............#

RUN mkdir /etc/service/wisemapping
ADD services/wisemapping.sh /etc/service/wisemapping/run
RUN chmod +x /etc/service/wisemapping/run

#...........................................#

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
