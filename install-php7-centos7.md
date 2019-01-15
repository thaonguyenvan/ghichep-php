# Hướng dẫn cài đặt php 7 trên Centos 7

- Cài đặt repo

```
# yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
# yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm
```

- Cài đặt yum-utils

`yum install yum-utils`

- Enable repo

`yum-config-manager --enable remi-php73`

- Cài đặt php và module liên quan

`yum install php php-mcrypt php-cli php-gd php-curl php-mysql php-ldap php-zip php-fileinfo `

- Kiểm tra lại sau khi cài đặt

`php -v`
