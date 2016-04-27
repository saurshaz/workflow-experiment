# Dockerfile for app at port 8000
FROM node:latest
EXPOSE 5000

RUN apt-get update
RUN apt-get install -y build-essential

RUN pwd
RUN rm -rf mycode/brackets
RUN mkdir -p mycode
RUN cd mycode
RUN git clone https://github.com/saurshaz/brackets.git
RUN cd brackets
RUN echo ' in brackets'
RUN ls -ll
RUN npm install
RUN echo 'setup app-two done on 8000'