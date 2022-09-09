# Zeeka-Project-Bazuka-Testnet

**Zeeka Bazuka Ödülsüz Node Testnet Kılavuzu**

![image](https://user-images.githubusercontent.com/98783018/189006873-f2a1cb6f-894d-477a-8e10-4b070845f140.png)

Sistem Gereksinimleri

```
2 CPU

2 RAM

50 SSD 
```

**libssl-dev kurulumu:**
```
sudo apt update

sudo apt install libssl-dev
```

**Cmake kurulumu:**
```
sudo apt-get install build-essential libssl-dev

cd /tmp

wget https://github.com/Kitware/CMake/releases/download/v3.20.0/cmake-3.20.0.tar.gz

tar -zxvf cmake-3.20.0.tar.gz

cd cmake-3.20.0

./bootstrap

make

sudo make install

cmake --version
```

**Version çıktısı şöyle olmalı:**

<img width="509" alt="image" src="https://user-images.githubusercontent.com/98783018/189353308-91dd8b4a-25f2-47e6-b518-25b99145a2db.png">

**Rust Kurulumu:**
```
sudo apt update

sudo apt upgrade

curl https://sh.rustup.rs -sSf | sh

source $HOME/.cargo/env

rustc --version
```
**Çıktı:**

<img width="439" alt="image" src="https://user-images.githubusercontent.com/98783018/189353690-37a3e3c0-b3ea-4de2-9b0b-c9cf8df1fdb8.png">

Bazuka clone kurulumu:

```
apt install git

git clone https://github.com/zeeka-network/bazuka
```

Devam

```
cd bazuka && cargo install --path .
```

Node Başlatıyoruz

```
bazuka init --seed 'metamask cüzdan kelime gir' --network debug --node 127.0.0.1:8765
```
NODE çalışması için bir sistem dosyası oluşturun

```
sudo tee <<EOF >/dev/null /etc/systemd/system/zeeka.service
[Unit]
Description=Zeeka node
After=network.target
[Service]
User=$USER
ExecStart=`RUST_LOG=info which bazuka` node --listen 0.0.0.0:8765 --external VPSGİR:8765 --network debug --db ~/.bazuka-debug --bootstrap 152.228.155.120:8765 --bootstrap 95.182.120.179:8765 --bootstrap 195.2.80.120:8765 --bootstrap 195.54.41.148:8765 --bootstrap 65.108.244.233:8765 --bootstrap 195.54.41.130:8765 --bootstrap 185.213.25.229:8765 --bootstrap 195.54.41.115:8765 --bootstrap 62.171.188.69:8765 --bootstrap 49.12.229.140:8765 --bootstrap 213.202.238.77:8765 --bootstrap 5.161.152.123:8765 --bootstrap 65.108.146.132:8765 --bootstrap 65.108.250.158:8765 --bootstrap 195.2.73.130:8765 --bootstrap 188.34.167.3:8765 --bootstrap 188.34.166.77:8765 --bootstrap 45.88.106.199:8765 --bootstrap 79.143.188.183:8765 --bootstrap 62.171.171.11:8765 --bootstrap 65.108.201.41:8765 --bootstrap 159.203.176.252:8765 --bootstrap 194.163.191.80:8765 --bootstrap 146.19.207.4:8765 --bootstrap 135.181.43.174:8765 --bootstrap 95.111.234.205:8765 --bootstrap 192.241.131.113:8765 --bootstrap 45.67.217.16:8765 --bootstrap 65.108.157.67:8765 --bootstrap 65.108.251.175:8765 --bootstrap 95.216.204.235:8765 --bootstrap 45.82.178.159:8765 --bootstrap 161.97.111.145:8765 --bootstrap 149.102.133.130:8765 --bootstrap 65.108.61.32:8765 --bootstrap 95.216.204.32:8765 --bootstrap 188.34.160.74:8765 --bootstrap 185.245.183.246:8765 --bootstrap 213.246.39.14:8765 --discord-handle “DİSCORDİSMİGİR”
Restart=on-failure
RestartSec=3
LimitNOFILE=65535
[Install]
WantedBy=multi-user.target
EOF
```

**Güncelleme:**

```
cd bazuka
git pull origin master
cargo install --path .
```

**Hizmetleri başlat**

```
sudo systemctl daemon-reload
sudo systemctl enable zeeka
sudo systemctl restart zeeka
```

**Log kontrol**

```
sudo journalctl -fu zeeka -o cat
```

Size verilen IP'i [discorda](https://discord.gg/VmhhkHzduD) resimle birlikte atmayı unutmayın

<img width="966" alt="image" src="https://user-images.githubusercontent.com/98783018/189356387-99b18f92-ef05-4d14-b1b5-02435d86630d.png">

Bizi Sosyal Medyadan Takip Etmeyi Unutma :)

Twitter | Telegram Duyuru | Telegram Chat | Youtube | Airdrop: Tek Link:https://linktr.ee/Cryptoloss
