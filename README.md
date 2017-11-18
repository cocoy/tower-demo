# Tower Demo using Apt-Cacher NG Server in PI 

## Background

Assume we have ang Ansible Tower running, we use this repo as Project on Tower in order to load the demo playbooks.

## Contents of this repo is
   1.  Setup the Docker host, it can be defined on the Tower Inventory setting the target IP/hostname to be our Docker Host. 
       After which set on template to run the playbook setup_docker_host.yml 
       The Docker hosts the Docker containers . 

   2. Playbook to create a docker container: apt-cache-ng. 
      What it does is to create an apt-cacher-ng inside a Docker Host. It means or target host here would be the hostname/IP of docker host above.
        The playbook is run_apt-cacher_container.yml

       This will run apt-cacher-ng on port 3142 of the docker host. 
	  
   3. Another playbook that will install apt-cacher-ng-client to target client hosts defined on new set of inventory file, to be apt-cacher client.
      Parameter on AWX Tower -> Templates -> Extra Variables: 

		site_url: http://apt.example.com:3142/

      Where: apt.example.com can be IP or dns of your apt-cacher-ng server.


## Author Information

Auther info goes here.
