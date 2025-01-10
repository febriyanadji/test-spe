# installasi mysql

## Centos

download repositori mysql :
```sh
curl -sSLO https://dev.mysql.com/get/mysql80-community-release-el7-5.noarch.rpm
```

install mysql server
```sh
sudo yum install mysql-server
```

jalankan mysql :
```sh
sudo systemctl start mysqld
```

atur password default root :
```sh
sudo mysql_secure_installation
```

## Ubuntu

update repositori:
```sh
sudo apt update
```

install paket mysql server :
```sh
sudo apt install mysql-server -y
```

jalankan mysql :
```sh
sudo systemctl start mysql.service
```

atur password root menggunakan perintah :
```sh
sudo mysql_secure_installation
```