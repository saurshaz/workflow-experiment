# Dockerfile for app at port 4000

FROM node:latest
EXPOSE 3000

RUN apt-get update
RUN apt-get install -y build-essential
RUN apt-get install -y build-essential curl  build-essential libssl-dev
RUN curl https://raw.githubusercontent.com/creationix/nvm/v0.30.0/install.sh | bash


RUN pwd
RUN mkdir -p /mycode
RUN mkdir -p /tmp/node_modules
RUN cd /mycode
RUN git clone https://github.com/saurshaz/applyx.git 

# Install http-server
RUN npm install -g http-server

# Define working directory
WORKDIR /mycode/applyx

# Provides cached layer for node_modules
# RUN cp -a /mycode/applyx/package.json /tmp/package.json
# RUN cd /tmp && npm install
# RUN cp -a /tmp/node_modules /mycode/applyx/
RUN cd /mycode/applyx && npm install && node server.js &

RUN echo ' in applyx'
RUN echo 'setup app-one done on 4000'


