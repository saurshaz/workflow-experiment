# Dockerfile for app at port 4000
FROM node:latest
EXPOSE 4000

RUN apt-get update
RUN apt-get install -y build-essential

RUN pwd
RUN rm -rf mycode/applyx
RUN mkdir -p mycode
RUN cd mycode
RUN git clone https://github.com/saurshaz/applyx.git && cd applyx

RUN  ' before npm install - applyx'
RUN pwd
RUN npm install

RUN echo 'setup app-one done on 4000'