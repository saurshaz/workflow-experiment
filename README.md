################################################
##            What is this ?                  ##
################################################
A note to self on what this is meant to be - 
- an experiment on 
- how multiple micro-services can be setup (remaining portable as a combination also)
- how dependencies resolving and orchastration process can be automated as much as possible

*Not to be used for your `dear` project (at least as of now)*
Please note plan is to wrap all below in s simply executable/launchable step


Steps :: (case study is 4 projects of mine)

- a fresh `ubuntu 12+` system with mongodb running
- get all the code by whatever means on 
- maintain .nvmrc file (node v4.2.0 and npm 3+ needed) 
- install `pm2`,`nodemon` globally
- link logging to papertrail for the system (TODO : :filter for the apps only later)
	`http://help.papertrailapp.com/kb/configuration/configuring-remote-syslog-from-unixlinux-and-bsdos-x/`
- install all dependencies in these apps(TODO :: make a SH script)
	- `fyler`,`applyx`,`riot-applyx` & `brackets`
- grab `ecosystem.json` from this repo
- run pm2 using `pm2 deploy <configuration_file> <environment> <command>`
- wrap the working setup in a `docker-compose.yaml` script


