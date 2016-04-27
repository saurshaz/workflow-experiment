# Dockerfile for app at port 5000
FROM node:latest
EXPOSE 5000

RUN apt-get update
RUN apt-get install -y build-essential

RUN pwd
RUN rm -rf mycode/Fyler
RUN mkdir -p mycode
RUN cd mycode
RUN git clone https://github.com/saurshaz/Fyler.git
RUN cd Fyler
RUN echo ' in Fyler'
RUN ls -ll
RUN npm install
RUN echo 'setup app-three done on 3000'