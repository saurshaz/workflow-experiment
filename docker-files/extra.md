# RUN ~/.nvm/nvm-exec install 5
# apt-get install docker python-pip apt-transport-https ca-certificates

#sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
#open /etc/apt/sources.list.d/docker.list
#add entry deb https://apt.dockerproject.org/repo ubuntu-trusty main
#sudo apt-get update
#sudo apt-get purge lxc-docker
#sudo apt-cache policy docker-engine
#sudo apt-get install docker-engine
#sudo nano /etc/default/grub 
#	add this here `GRUB_CMDLINE_LINUX="cgroup_enable=memory swapaccount=1"`
#sudo update-grub
#sudo docker run hello-world
#pip install docker-compose --upgrade
# pip install docker-compose