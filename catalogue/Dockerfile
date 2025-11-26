FROM node:20.19.6-alpine3.22 AS build
WORKDIR /opt/server/
COPY package.json .
COPY server.js .
RUN npm install

FROM node:20.19.6-alpine3.22 
WORKDIR /opt/server/
COPY --from=build --chown=roboshop:roboshop /opt/server /opt/server
ENV MONGO=true
ENV MONGO_URL="mongodb://mongodb:27017/catalogue"
CMD ["node", "server.js"]

# FROM node:20
# WORKDIR /opt/server/
# COPY package.json .
# COPY server.js .
# RUN npm install
# ENV MONGO=true
# ENV MONGO_URL="mongodb://mongodb:27017/catalogue"
# CMD ["node", "server.js"]