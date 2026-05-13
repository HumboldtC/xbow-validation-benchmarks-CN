FROM node:16-alpine

RUN sed -i 's|dl-cdn.alpinelinux.org|mirrors.aliyun.com|g' /etc/apk/repositories \
    && apk --no-cache add curl

WORKDIR /app
COPY . .
RUN npm install --registry=https://registry.npmmirror.com
EXPOSE 8333
CMD [ "npm", "start" ]
