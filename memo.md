# wsl_setup

```Windows
wsl --install -d Ubuntu
wsl --install -d Debian
```

## Buralit
```Ubuntu
sudo apt update && sudo apt upgrade -y
```

- NodeJS
```Ubuntu
curl https://get.volta.sh | bash
volta install node
```

- AWS
```
sudo apt -y install unzip jq
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws --version
```

- Docker
```
# Add Docker's official GPG key:
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
sudo apt-get -y install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

```
sudo groupadd docker
sudo gpasswd -a $USER docker
sudo systemctl restart docker
exit
```

```
wsl --shutdown
```

- Git clone
```
git clone https://{your_token}@github.com/xr-campus-dev/BURALIT-backend-v2
cd BURALIT-backend-v2
git checkout refs/tags/v2_20241025
```

```
cd BURALIT-backend-v2
npm i
docker compose up -d
```

```
bash ./scripts/clean-local-db-test.sh
bash ./scripts/create-cognito-pool-on-moto.sh
```

```
npm run prisma:pull:dev
npm run prisma:gen:dev
cd ./database/prisma
npx prisma generate
```

```
cd ../../
git checkout src/__generated__/fabbrica/index.ts
```
```
bash ./scripts/clean-local-db-for-server.sh
bash ./scripts/create-admin-spotowner-user.sh
```

```
curl -X PUT -H "Content-Type: application/json" -d @opensearch/_index_template/exit-group-template.json "http://localhost:9200/_index_template/exit-group-template"
curl -X PUT -H "Content-Type: application/json" -d @opensearch/_index_template/logs-template.json "http://localhost:9200/_index_template/logs-template"
curl -X PUT -H "Content-Type: application/json" -d @opensearch/_index_template/userevent-template.json "http://localhost:9200/_index_template/userevent-template"

bash ./scripts/create-opensearch-index-and-mapping.sh
```

- pgadmin
```
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg

# Create the repository configuration file:
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'

#
# Install pgAdmin
#

# Install for both desktop and web modes:
sudo apt install pgadmin4

# Configure the webserver, if you installed pgadmin4-web:
sudo /usr/pgadmin4/bin/setup-web.sh
```

```
git clone https://{your_token}@github.com/xr-campus-dev/BURALIT-R3F-test-util

```

```
curl -sSL https://get.livekit.io | bash
```

---

## 
```Ubuntu
sudo apt -y install openssh-server
sudo service ssh restart
```

```Debian
sudo apt update && sudo apt upgrade -y
sudo apt -y install openssh-client
```

## 接続確認
- IPを確認
```Ubuntu
hostname -I
```

- SSH接続
```Debian
ssh ユーザー名@接続先のIPアドレス
```

## Ansibleセットアップ
- 以下の行を /etc/apt/sources.list に追加します。
```
deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main
```

```Debian
sudo apt install gnupg
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367
sudo apt update
sudo apt install ansible
```

```Debian
sudo apt install git

```
