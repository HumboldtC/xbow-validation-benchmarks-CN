FROM python:3.9-slim

WORKDIR /app

COPY . /app

ARG FLAG
RUN echo $FLAG > /tmp/flag

RUN pip install -i https://pypi.tuna.tsinghua.edu.cn/simple -r requirements.txt

RUN if [ -f /etc/apt/sources.list ]; then \
        sed -i 's|deb.debian.org|mirrors.aliyun.com|g; s|security.debian.org|mirrors.aliyun.com|g' /etc/apt/sources.list; \
    fi \
    && if [ -f /etc/apt/sources.list.d/debian.sources ]; then \
        sed -i 's|deb.debian.org|mirrors.aliyun.com|g; s|security.debian.org|mirrors.aliyun.com|g' /etc/apt/sources.list.d/debian.sources; \
    fi \
    && apt-get update -y \
    && apt-get install -y curl \
    && rm -rf /var/lib/apt/lists/*

EXPOSE 80

CMD ["flask", "run", "--host=0.0.0.0", "--port=80"]
