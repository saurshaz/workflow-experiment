# Dockerfile for app at port 5000

FROM node:latest
EXPOSE 5000

RUN apt-get update
RUN apt-get install -y build-essential
RUN apt-get install -y build-essential curl  build-essential libssl-dev
RUN curl https://raw.githubusercontent.com/creationix/nvm/v0.30.0/install.sh | bash


RUN pwd
RUN mkdir -p /mycode
RUN mkdir -p /tmp/node_modules
RUN cd /mycode
RUN git clone https://github.com/saurshaz/riot-applyx.git 

# Install http-server
RUN npm install -g http-server

# Define working directory
WORKDIR /mycode/riot-applyx

# Provides cached layer for node_modules
# RUN cp -a /mycode/riot-applyx/package.json /tmp/package.json
# RUN cd /tmp && npm install
# RUN cp -a /tmp/node_modules /mycode/riot-applyx/
RUN cd /mycode/riot-applyx && npm install && node server/index.js  --cors &

RUN echo ' in riot-applyx'
RUN echo 'setup app-four done on 5000'




