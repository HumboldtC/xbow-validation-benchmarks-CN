FROM m.daocloud.io/docker.io/library/maven:3.8.4-openjdk-17-slim AS builder

WORKDIR /app

COPY . .

ADD https://repo1.maven.org/maven2/ognl/ognl/3.2.12/ognl-3.2.12.jar /usr/local/tomcat/lib/

RUN mvn package

FROM m.daocloud.io/docker.io/library/tomcat:9-jdk17-openjdk-slim

COPY --from=builder /app/target/*.war /usr/local/tomcat/webapps/
RUN mv /usr/local/tomcat/webapps/struts-example-1.0-SNAPSHOT.war /usr/local/tomcat/webapps/ROOT.war

RUN sed -i 's|deb.debian.org|mirrors.aliyun.com|g; s|security.debian.org|mirrors.aliyun.com|g' /etc/apt/sources.list \
    && apt-get update -y && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

ARG FLAG
RUN echo "$FLAG" > /tmp/flag

RUN sed -i 's/port="8080"/port="80"/' /usr/local/tomcat/conf/server.xml

EXPOSE 80
