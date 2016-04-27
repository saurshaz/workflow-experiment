# Dockerfile for app at port 8000
FROM node:latest
EXPOSE 7000

RUN apt-get update
RUN apt-get install -y build-essential
RUN apt-get install -y build-essential curl  build-essential libssl-dev
RUN curl https://raw.githubusercontent.com/creationix/nvm/v0.30.0/install.sh | bash


RUN pwd
RUN mkdir -p /mycode
RUN mkdir -p /tmp/node_modules
RUN cd /mycode
RUN git clone https://github.com/saurshaz/brackets.git 

# Install http-server
RUN npm install -g http-server

# Define working directory
WORKDIR /mycode/brackets

# Provides cached layer for node_modules
# RUN cp -a /mycode/brackets/package.json /tmp/package.json
# RUN cd /tmp && npm install
# RUN cp -a /tmp/node_modules /mycode/brackets/
RUN cd /mycode/brackets && npm install && http-server -p 7000 --cors &

RUN echo ' in brackets'
RUN echo 'setup app-two done on 7000'


