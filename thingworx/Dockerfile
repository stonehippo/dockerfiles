FROM tomcat:8.5
MAINTAINER George White <stonehippo@gmail.com>

ENV CATALINA_OPTS -XX:PermSize=128m -XX:MaxPermSize=1024m -XX:+UseNUMA -XX:+UseConcMarkSweepGC

# set up a manager user for tomcat
# use org.apache.coyote.http11.Http11NioProtocol protocol for better websocket
# performance
COPY ./config/tomcat-users.xml ./config/server.xml /usr/local/tomcat/conf/
RUN chmod go= /usr/local/tomcat/conf/tomcat-users.xml /usr/local/tomcat/conf/server.xml

# allow remote access to the tomcat manager app
COPY ./config/manager-context.xml /usr/local/tomcat/webapps/manager/META-INF/context.xml
RUN chmod g=o=r /usr/local/tomcat/webapps/manager/META-INF/context.xml

# place Thingworx for deployment
COPY ./webapps/Thingworx.war /usr/local/tomcat/webapps

EXPOSE 8080
