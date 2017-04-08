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
interface: 192.168.99.1
```
