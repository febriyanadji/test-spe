
# Cara installasi docker & docker compose 
## Centos 7

update package database :
```sh
sudo yum check-update
```

tambah official docker repository :
```sh
curl -fsSL https://get.docker.com/ | sh
```

hidupkan service docker :
```sh
sudo systemctl start docker
```

aktifkan auto start ketika booting :
```sh
sudo systemctl enable docker
```

agar dapat eksekusi perintah docker tanpa sudo :
```sh
sudo usermod -aG docker $(whoami)
```

download binary docker compose :
```sh
sudo curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

atur permission agar dapat dieksekusi :
```sh
sudo chmod +x /usr/local/bin/docker-compose
```

## Ubuntu

tambah repositori docker :
```sh
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

install docker & docker compose :
```sh
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

agar dapat eksekusi perintah docker tanpa sudo :
```sh
sudo usermod -aG docker $(whoami)
```