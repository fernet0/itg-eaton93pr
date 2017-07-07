FROM telegraf
#RUN sed -i "/^#.*deb.*multiverse$/s/^# //g" /etc/apt/sources.list
RUN echo "deb http://archive.ubuntu.com/ubuntu/ trusty multiverse" >> /etc/apt/sources.list && \
	apt-get update && apt-get -y install snmp snmp-mibs-downloader && download-mibs
RUN rm -rf /var/cache/apt
COPY telegraf.conf /etc/telegraf
