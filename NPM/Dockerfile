FROM node:10

RUN  apk add --update tini

# Create app directory
WORKDIR -p /usr/src/app

# Install app dependencies
COPY package*.json ./

RUN npm install && npm cache clean --force

COPY . .

EXPOSE 8080
CMD [ "/sbin/tini","-- node","./bin/www" ]