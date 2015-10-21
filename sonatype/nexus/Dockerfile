FROM gsacsp-build02.reisys.com:5000/library/oracle-jdk8

MAINTAINER Chris Edwards "cedwards@reisystems.com"

RUN mkdir -p /opt/sonatype-nexus /opt/sonatype-work-template /opt/sonatype-work
RUN wget -O /tmp/nexus-latest-bundle.tar.gz http://download.sonatype.com/nexus/oss/nexus-3.0.0-m5-bundle.tar.gz
RUN tar xzvf /tmp/nexus-latest-bundle.tar.gz -C /opt/sonatype-nexus --strip-components=1
RUN useradd --user-group --system --home-dir /opt/sonatype-nexus nexus
RUN chown -R nexus:nexus /opt/sonatype-work-template /opt/sonatype-work /opt/sonatype-nexus
ENV NEXUS_WEBAPP_CONTEXT_PATH /
ADD start_as_nexus.sh /opt/start_as_nexus.sh
ADD start_nexus.sh /opt/start_nexus.sh
RUN ln -s /opt/start_nexus.sh /opt/start.sh

CMD ["/opt/start_as_nexus.sh"]
VOLUME /opt/sonatype-work
EXPOSE 8081
