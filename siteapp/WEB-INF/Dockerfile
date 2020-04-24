FROM alpine:latest
#FROM centos:latest
# CentOS Linux release 8.0.1905
MAINTAINER "walter <daiming@zainanjing365.com>"

#COPY tomcat7057 /usr/local/instance/{{city_name}}/{{project_name}}/tomcat7057/
COPY jdk1.7.0_67 /usr/local/jdk1.7.0_67/
#COPY crond cronolog /usr/sbin/

#COPY siteapp.war websocket.war schedule.war  /usr/local/instance/{{city_name}}/{{project_name}}/tomcat7057/webapps/

ENV JAVA_HOME=/usr/local/jdk1.7.0_67
ENV JRE_HOME=$JAVA_HOME/jre
ENV CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$JRE_HOME/lib:$CLASSPATH
ENV PATH=/usr/sbin:$JAVA_HOME/bin:$PATH

#ENV TZ=Asia/Shanghai
#ENV LANG C.UTF-8
#RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo '$TZ' > /etc/timezone
RUN sed -i "s/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g" /etc/apk/repositories \
&&  apk add --no-cache tzdata \
&&  cp -rf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
&&  apk del tzdata

#WORKDIR /usr/local/instance/tomcat7057/

#EXPOSE {{java_port}}/tcp
#EXPOSE {{jmx_port}}/tcp

#ENTRYPOINT ["/usr/local/instance/{{city_name}}/{{project_name}}/tomcat7057/bin/catalina.sh","run"]

