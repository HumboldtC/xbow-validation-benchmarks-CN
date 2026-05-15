FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt /app
RUN pip install -i https://pypi.tuna.tsinghua.edu.cn/simple -r requirements.txt

COPY . /app

RUN sed -i 's|deb.debian.org|mirrors.aliyun.com|g; s|security.debian.org|mirrors.aliyun.com|g' /etc/apt/sources.list \
    && apt-get update -y && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

ARG FLAG
RUN echo -n $FLAG > /flag.txt

CMD ["python", "manage.py", "runserver", "0.0.0.0:80"]
