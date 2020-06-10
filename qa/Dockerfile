FROM fitltd/lifefitwebbase:latest
LABEL maintainer="Justin Emina \"justin.emina@fitltd.com\""

COPY Catalina /opt/lifefit/tomcat/conf/Catalina
COPY server.xml /opt/lifefit/tomcat/config/server.xml
COPY winnt /opt/lifefit/winnt
COPY www_webqa_fitltd_com.jks /opt/lifefit/tomcat/conf/www_webqa_fitltd_com.jks
WORKDIR /opt/lifefit/qa/webapps
RUN curl -O http://gitlab.fitltd.com:8083/artifactory/libs-release/com/fitltd/lifefit/186-Alpha/lifefit-186-Alpha.war
RUN jar xvf lifefit-186-Alpha.war
RUN  chmod 775 /opt/lifefit/qa/log

