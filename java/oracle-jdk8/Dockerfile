FROM centos

MAINTAINER Chris Edwards <cedwards@reisystems.com>

RUN yum update -y

RUN curl --insecure --junk-session-cookies --location --remote-name --silent --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8-b132/jdk-8-linux-x64.rpm

RUN yum localinstall -y jdk-8-linux-x64.rpm
RUN rm jdk-8-linux-x64.rpm

ENV JAVA_HOME /usr/java/default

# Define default command.
CMD ["bash"]
