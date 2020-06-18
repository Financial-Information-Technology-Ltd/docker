FROM fitltd/lifefitwebbase:latest
LABEL maintainer="Justin Emina \"justin.emina@fitltd.com\""
ARG buildVersion
COPY Catalina /opt/lifefit/tomcat/conf/Catalina
COPY server.xml /opt/lifefit/tomcat/config/server.xml
COPY winnt /opt/lifefit/winnt
COPY www_webqa_fitltd_com.jks /opt/lifefit/tomcat/conf/www_webqa_fitltd_com.jks
WORKDIR /opt/lifefit/qa/webapps
RUN echo "${buildVersion}"
RUN curl -O http://gitlab.fitltd.com:8083/artifactory/libs-release/com/fitltd/lifefit/$buildVersion/lifefit-$buildVersion.war
RUN jar xvf lifefit-$buildVersion.war
RUN  chmod 775 /opt/lifefit/qa/log

