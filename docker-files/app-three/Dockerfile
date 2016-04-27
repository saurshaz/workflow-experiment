# Dockerfile for app at port 3000

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
RUN git clone https://github.com/saurshaz/Fyler.git 

# Install http-server
RUN npm install -g http-server

# Define working directory
WORKDIR /mycode/Fyler

# Provides cached layer for node_modules
# RUN cp -a /mycode/Fyler/package.json /tmp/package.json
# RUN cd /tmp && npm install
# RUN cp -a /tmp/node_modules /mycode/Fyler/
RUN cd /mycode/Fyler && npm install && node server.js --cors &

RUN echo ' in Fyler'
RUN echo 'setup app-three done on 3000'


