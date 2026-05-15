FROM docker.1ms.run/node:21

WORKDIR /app

COPY package*.json ./

RUN npm config set registry https://registry.npmmirror.com && npm install

COPY . .

EXPOSE 80

ARG FLAG
ENV FLAG=${FLAG}
CMD ["node", "server.js"]
