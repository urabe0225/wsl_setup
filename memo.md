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

