# base image
FROM node:12.14.0-alpine

# install global packages
ENV NPM_CONFIG_PREFIX=/home/node/.npm-global
RUN npm install npm@latest -g
RUN npm install react-scripts@3.3.0 -g

# set working directory
WORKDIR /usr/src/app

# install dependencies
COPY package*.json /usr/src/app/
ENV PATH /usr/src/app/node_modules/.bin:$PATH
ENV PATH=$PATH:/home/node/.npm-global/bin
RUN npm ci

# start app
CMD ["./node_modules/.bin/react-scripts", "start"]
