FROM httpd:2.4.49

RUN echo "deb [trusted=yes] http://mirrors.aliyun.com/debian-archive/debian/ buster main" > /etc/apt/sources.list && \
    echo "deb [trusted=yes] http://mirrors.aliyun.com/debian-archive/debian-security/ buster/updates main" >> /etc/apt/sources.list

COPY ./httpd.conf /usr/local/apache2/conf/httpd.conf

RUN apt-get update -y && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

ARG FLAG
RUN echo $FLAG > /tmp/flag
