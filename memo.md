# wsl_setup

```Windows
wsl --install -d Ubuntu
wsl --install -d Debian
```

```Ubuntu
sudo apt update && sudo apt upgrade -y
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
