ARG LARADOCK_NODE_VERSION=latest
# FROM node:${LARADOCK_NODE_VERSION}-alpine
FROM node:alpine

LABEL maintainer="Huadong Zuo <admin@zuohuadong.cn>"

ENV CHROME_BIN=/usr/bin/chromium-browser
RUN echo @edge http://nl.alpinelinux.org/alpine/edge/community >> /etc/apk/repositories && \
    echo @edge http://nl.alpinelinux.org/alpine/edge/main >> /etc/apk/repositories && \
    apk add --no-cache \
      chromium@edge \
      nss@edge

RUN apk --no-cache add tzdata ca-certificates && npm install pm2@latest -g 

RUN npm install pm2 -g

WORKDIR /var/www/node.js

EXPOSE 5000-5000

# CMD ["pm2-runtime", "npm","--","start"]

CMD ["pm2-runtime", "index.js"]
