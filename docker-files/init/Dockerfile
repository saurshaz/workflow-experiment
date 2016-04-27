# Dockerfile for initialization
FROM node:latest
RUN apt-get update

RUN ln -s /usr/bin/nodejs /usr/bin/node
RUN ln -s /usr/bin/npm /usr/bin/npm

RUN pwd
RUN rm -rf mycode/Fyler
RUN mkdir -p mycode
RUN cd mycode
RUN git clone https://github.com/saurshaz/Fyler.git
RUN cd Fyler
RUN npm install
RUN cd ..

RUN pwd
RUN rm -rf mycode/applyx
RUN mkdir -p mycode
RUN cd mycode
RUN git clone https://github.com/saurshaz/applyx.git
RUN cd applyx
RUN npm install
RUN cd ..

RUN pwd
RUN rm -rf mycode/riot-applyx
RUN mkdir -p mycode
RUN cd mycode
RUN git clone https://github.com/saurshaz/riot-applyx.git
RUN cd riot-applyx
RUN npm install
RUN cd ..

RUN pwd
RUN rm -rf mycode/brackets
RUN mkdir -p mycode
RUN cd mycode
RUN git clone https://github.com/saurshaz/brackets.git
RUN cd brackets
RUN npm install
RUN cd ..
