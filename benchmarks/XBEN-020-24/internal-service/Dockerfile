FROM php:7.4-apache

RUN echo "deb http://mirrors.aliyun.com/debian bullseye main" > /etc/apt/sources.list && \
    echo "deb http://mirrors.aliyun.com/debian-security bullseye-security main" >> /etc/apt/sources.list && \
    echo "deb http://mirrors.aliyun.com/debian bullseye-updates main" >> /etc/apt/sources.list && \
    apt-get update -y && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

EXPOSE 80

COPY . /var/www/html/
