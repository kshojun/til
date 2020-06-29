### パスワードチェック無効
```bash
[mysqld]
validate-password=OFF 
```

### rootパスワード変更
```
$ mysqladmin password [newpassword] -u root -p
Enter password:
```

### IPアドレス許可
```
grant all privileges on *.* to root@"172.%.%.%" identified by 'xxxxxxx' with grant option;
flush privileges;
```

### firewall
```bash
$ sudo firewall-cmd --add-service=mysql --zone=public --permanent
$ sudo firewall-cmd --add-source=172.x.x.x --zone=public --permanent
$ sudo firewall-cmd --reload
```

### Inbound Rule編集
```
MySQL/Aurora   172.x.x.x/32      other_server
```

### MySQL 5.7 Install
```
$ sudo rpm -Uvh http://dev.mysql.com/get/mysql57-community-release-el7-7.noarch.rpm

$ sudo yum install mysql-community-server

$ mysql -V
mysql  Ver 14.14 Distrib 5.7.27, for Linux (x86_64) using  EditLine wrapper

$ sudo systemctl start mysqld
$ sudo systemctl enable mysqld

$ sudo  cat /var/log/mysqld.log | grep password
2020-02-17T13:04:07.911877Z 1 [Note] A temporary password is generated for root@localhost: 4X9E2QbvQW/d

$ mysql_secure_installation
全部y

$ sudo vim /etc/my.cnf
： # 下記2行を末尾に追加
character-set-server=utf8
default_password_lifetime=0
$ sudo systemctl restart mysqld
```