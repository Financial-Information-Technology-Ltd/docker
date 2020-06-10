FROM ubuntu:20.04
LABEL maintainer="Justin Emina \"justin.emina@fitltd.com\""
RUN apt update && apt install -y openjdk-8-jdk && apt install -y locales locales-all && apt install -y iputils-ping && apt install -y wget && apt install -y curl
RUN mkdir /opt/lifefit
RUN mkdir /opt/lifefit/tomcat
RUN mkdir /opt/lifefit/winnt
RUN mkdir /opt/lifefit/qa
RUN mkdir /opt/lifefit/qa/webapps
RUN mkdir /opt/lifefit/qa/log
RUN mkdir /opt/lifefit/webapps

WORKDIR /opt/lifefit/tomcat/
RUN curl -O https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.35/bin/apache-tomcat-9.0.35.tar.gz
RUN tar xvfz apache*.tar.gz
RUN mv apache-tomcat-9.0.35/* /opt/lifefit/tomcat/.
ENV LC_ALL C.UTF-8
ENV LANG C.UTF-8
ENV LANGUAGE C.UTF-8
ENV JPDA_ADDRESS="5005"
ENV JPDA_TRANSPORT="dt_socket"
EXPOSE 8080 5005

CMD ["/opt/lifefit/tomcat/bin/catalina.sh", "jpda","run"]

