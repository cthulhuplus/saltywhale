# saltywhale
SaltyWhale is my home project to set up a containerized environment to learn more about Salt and Docker in particular, but also enable myself to spin up other containerized services that I can explore.

### Master
The Salt Master will contain:
* salt-master
* salt-minion
* salt-ssh
* salt-cloud (optional)
* salt-syndic (optional)
* docker
* sysdig
* graylog

I am setting up Sysdig and Graylog to monitor my infrastructure and to learn about these solutions.  SysDig is a monitoring tool specializing in containers.  Graylog is a logging tool. 

### Minion

## Goals
* Use Salt to create an Infrastructure as Code Docker environment
  * I should be able to redeploy this entire enviroment using salt

## Issues
* Database storage/backup, how to do this as IaC

## Resources
https://sysdig.com/
https://www.graylog.org/
