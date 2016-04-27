# Dockerfile for app at port 5000
FROM node:latest
EXPOSE 5000

RUN apt-get update
RUN apt-get install -y build-essential

RUN pwd
RUN rm -rf mycode/riot-applyx
RUN mkdir -p mycode
RUN cd mycode
RUN git clone https://github.com/saurshaz/riot-applyx.git
RUN cd riot-applyx
RUN  ' before npm install - riot-applyx'
RUN pwd
RUN npm install



RUN echo 'setup app-four done on 5000'

