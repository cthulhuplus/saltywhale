# SaltStack
Set up the salt repository
```
/etc/yum.repos.d/saltstack.repo

[saltstack-repo]
name=SaltStack repo for Red Hat Enterprise Linux $releasever
baseurl=https://repo.saltstack.com/yum/redhat/$releasever/$basearch/latest
enabled=1
gpgcheck=1
gpgkey=https://repo.saltstack.com/yum/redhat/$releasever/$basearch/latest/SALTSTACK-GPG-KEY.pub
       https://repo.saltstack.com/yum/redhat/$releasever/$basearch/latest/base/RPM-GPG-KEY-CentOS-7
```

Install SaltStack
```
sudo yum install -y salt-master
sudo yum install -y salt-minion
sudo yum install -y salt-ssh
sudo yum install -y salt-syndic
sudo yum install -y salt-cloud
```

Enable Salt-Master on Boot
```
sudo systemctl enable salt-master.service
sudo systemctl start salt-master.service
```

Enablel Salt-Minion on Boot (Goes on the Master too)
```
sudo systemctl enable salt-minion.service
sudo systemctl enable salt-minion.service
```

```
# Did not work
interface: 192.168.99.1
interface: 0.0.0.0
```

Make the directory structure
```
sudo mkdir /srv/salt
sudo mkdir /srv/pillar
```

The pillar directory is where secrets are stored so that they do not need to be place in salt states in plain text

Allow salt to run as a user
```
sudo chown -R vagrant /etc/salt /var/cache/salt /var/log/salt /var/run/salt /srv/salt /srv/pillar
```

Tell salt that your user (in this case vagrant) is allowed to run it

```
/etc/salt/master
user: vagrant

sudo systemctl restart salt-master

salt '*' test.ping
10.0.2.15:
    True
```

## TODO
### Create a salt state for the master
* Install Salt
  * Manage configurations
  * Set up salt to be run as the user
* Install Docker
  * Set Docker to be set up as the user
  * Set up critical Containers
    * SysDig
    * Graylog
    * Consul(?)
    * Vault(?)

### Create a salt state foro the minion
* Install Salt
  * Manage configurations
  * Set up salt to be run as the user 
* Install Docker
  * Set Docker to be set up as the user
  * Set up Containers
    * SysDig
    * Graylog
    * Consul Client(?)
    * Apache
    * MySQL
* Apply Salt State using salt-ssh
