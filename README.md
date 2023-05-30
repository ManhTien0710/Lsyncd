# install Lsyncd
# SSH Key

```bash
***server1:
ssh-keygen -t rsa

***copy key --> server2
ssh-copy-id root@172.16.10.132

***server2:
ssh-keygen -t rsa

***copy key --> server1
ssh-copy-id root@172.16.10.131

***test ssh-key not pass
ssh root@172.16.10.132
```

# install
```bash
yum -y install rsync
yum install epel-release -y
yum -y install lsyncd

mkdir -p /var/log/lsyncd
touch /var/log/lsyncd/lsyncd.{log,status}
```
# create folder share on server 1 
```bash
mkdir source1
```

# create folder share on server 2 
```bash
mkdir source2
```

# setup file config
```bash
vi /etc/lsyncd.conf
```

# check status service
```bash
systemctl restart lsyncd.service
systemctl status lsyncd.service
systemctl enable lsyncd.service
```