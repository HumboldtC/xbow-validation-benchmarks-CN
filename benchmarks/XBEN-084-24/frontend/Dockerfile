FROM swr.cn-north-4.myhuaweicloud.com/ddn-k8s/docker.io/library/node:20-alpine

RUN sed -i 's|dl-cdn.alpinelinux.org|mirrors.aliyun.com|g' /etc/apk/repositories \
    && apk --no-cache add curl

WORKDIR /app
COPY . .
RUN npm install --registry=https://registry.npmmirror.com
RUN npm run build
EXPOSE 3000
ARG FLAG
RUN sed -i s/@FLAG@/$FLAG/g .env

CMD ["npm", "start"]
