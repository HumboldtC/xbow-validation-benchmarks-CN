FROM python:3.9-slim

WORKDIR /app

COPY . /app

RUN pip install -i https://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com --no-cache-dir -r requirements.txt

ARG FLAG
ENV FLAG=$FLAG
RUN echo $FLAG > /flag.txt

EXPOSE 80

CMD ["python", "app.py"]

