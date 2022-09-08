# Zeeka-Project-Bazuka-Testnet

**Zeeka Bazuka Ödülsüz Node Testnet Kılavuzu**

![image](https://user-images.githubusercontent.com/98783018/189006873-f2a1cb6f-894d-477a-8e10-4b070845f140.png)

Sistem Gereksinimleri

```
2 CPU

2 RAM

50 SSD 
```

**libssl-dev kurarak başlıyoruz:**

```
sudo apt update && sudo apt upgrade -y
sudo apt install curl tar wget clang pkg-config libssl-dev jq build-essential bsdmainutils git 
make ncdu gcc git jq chrony liblz4-tool -y
```

**Alacağınız çıktı:**

<img width="472" alt="image" src="https://user-images.githubusercontent.com/98783018/189007525-d45b811b-dabb-4ced-a91b-4ab529810fd8.png">

**cmake kuruyoruz:**

```
sudo apt install cmake -y
```

**ÇIKTI**

<img width="514" alt="image" src="https://user-images.githubusercontent.com/98783018/189007657-955ea48b-01f7-49f2-9583-e130769b8b58.png">

**rustup'ı kuruyoruz:**

_Kurulum tamamlandıktan sonra 1'e basıp enterliyoruz_

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

<img width="391" alt="image" src="https://user-images.githubusercontent.com/98783018/189007848-570847b9-9f8f-40b4-8ff2-dde2a0f90cfe.png">

**ÇIKTI**

<img width="652" alt="image" src="https://user-images.githubusercontent.com/98783018/189007962-342ba607-02a2-4375-8149-a4654fd0e4b5.png">

**Git Kuralım**
```
apt install git
```

**git clone çekiyoruz:**

```
git clone https://github.com/zeeka-network/bazuka
```

Cargo kurulumu (y bas)

```
apt install cargo -y
```

**Path Kurulumu**

```
cd
cd bazuka && cargo install --path .
```

**Seed Ekliyoruz**
```
bazuka init --seed 38b4d78c7d6582fb170f6c19330a7e37e6964212@rues.forum.info:8765 --network debug --node 127.0.0.1:8765
```

**Nodu Kuruyoruz:**

_your external ip kısmını sunucu ip'inizi girin ve daha sonra parantezleri kaldırın_

```
bazuka node --listen 0.0.0.0:8765 --external [your external ip]:8765 \

  --network debug --db ~/.bazuka-debug --bootstrap [bootstrap node 1] --bootstrap [bootstrap node 2] ...
```
