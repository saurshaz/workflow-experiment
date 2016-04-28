################################################
##            What is this ?                  ##
################################################
A note to self on what this is meant to be - 
- an experiment on 
- how multiple micro-services can be setup (remaining portable as a combination also)
- how dependencies resolving and orchastration process can be automated as much as possible

*Not to be used for your `dear` project (at least as of now)*
Please note plan is to wrap all below in s simply executable/launchable step


Steps :: (case study is 4 projects of mine ... can be anything)

- a fresh `ubuntu 12+` system with mongodb running
- get all the code by whatever means on 
- maintain .nvmrc file (node v4.2.0 and npm `3.8.7` needed) 
- install `pm2`,`nodemon` , `http-server`,`gulp`,`webpack` globally
- link logging to papertrail for the system (TODO : :filter for the apps only later)
	`http://help.papertrailapp.com/kb/configuration/configuring-remote-syslog-from-unixlinux-and-bsdos-x/`
- install all dependencies in these apps(TODO :: make a SH script)
	- `fyler`,`applyx`,`riot-applyx` & `brackets`
- grab `ecosystem.json` from this repo
- run pm2 using `pm2 deploy <configuration_file> <environment> <command>`
- wrap the working setup in a `docker-compose.yaml` script




# Docker Packaging :: Steps
---------------------------------------------------------------------------------------------------------------------
- start with a docker image of `nginx` + `mongodb` + `redis` + `elasticsearch`
- install `node`
- install `nvm` 
- install `pm2` globally
- have different microservices as nested `docker containers` 
	- `git clone` steps to get all the code in different folders
	- do not install `webpack` or `gulp` or anything else globally. use `node_modules\.bin\webpack` syntax
	- install dependencies `npm i` and  `bower i` with proper `node` & `npm` version switching
- clone `ecosystem.json` for pm2
- start everything with `pm2`
- setup remote_logging with `papertrail` via installing 
	- `remote_syslog` 
	- and creating `/etc/log_files.yml`
- give right permissions to any shell script or executable run from anywhere
- all errors shal be `noisy`, nothing silent
- send an email upon successful deploy. use a shell script with `mailgun api key`


# Possible approaches
---------------------------------------------------------------------------------------------------------------------
- Docker microservices approach(flavour 1)
	- 4 Docker containers (each running one app) 
	- and one for mongo and nginx each 
	- all wrapped and starable with one docker-compose.yml
	- the fetching of code is also part of the containers only. No src code linked here
- Docker microservices approach(flavour 2)
	- 4 Docker containers (each running one app) 
	- and one for mongo and nginx each 
	- all wrapped and starable with one docker-compose.yml
	- the fetching of code is NOT part of the app containers bootstrapping here. src code fetched before and linked here as volumes
- Less automatied but working approach.shell based
	- code fetch done using one shell script 
	- pm2 ecosystem.json file also fetched
	- pm2-gui, with a .ini setup
	- environemnt specific pm2 launched which starts everything (this is app only automation)
	- all non-app automation done using shell scripts


- Circle CI/jenkins + Github + Mocha based automation post stability (manual triggers in stage, push based automated after that )

