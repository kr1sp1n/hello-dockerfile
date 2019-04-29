FROM node:lts-alpine
WORKDIR /app
# install tini (https://github.com/krallin/tini)
RUN apk add --no-cache tini
# `./` refers to WORKDIR
COPY package.json yarn.lock ./
RUN yarn
COPY src ./src
ENTRYPOINT ["/sbin/tini", "--"]
CMD ["node", "."]
