FROM	debian:wheezy

ENV	DEBIAN_FRONTEND noninteractive 
# karaf ssh
EXPOSE	8101
# webconsole
EXPOSE	8181
VOLUME	['/data/karaf-data']

RUN	apt-get update -y && apt-get install -y wget openjdk-7-jdk
RUN	mkdir -p /data/karaf-data && cd /data && wget -q http://mirror.tcpdiag.net/apache/karaf/3.0.3/apache-karaf-3.0.3.tar.gz && tar xvzf apache-karaf-3.0.3.tar.gz

COPY	org.apache.karaf.features.cfg /data/apache-karaf-3.0.3/etc/org.apache.karaf.features.cfg
COPY	system.properties /data/apache-karaf-3.0.3/etc/system.properties

CMD	/data/apache-karaf-3.0.3/bin/karaf server

