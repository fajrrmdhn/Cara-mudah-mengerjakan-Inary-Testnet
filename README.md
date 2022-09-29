# Cara-mudah-mengerjakan-Inary-Testnet
Pertama tama saya akan menjelaskan apa itu Inery. Inery mewakili database terdistribusi dengan sinergi blockchain yang diadopsi untuk memanfaatkan teknologi blockchain untuk mendesentralisasi data sementara, pada saat yang sama, mengurangi pelanggaran data dan memastikan keamanan. Pendekatan ini mengamankan data pengguna dan memiliki penggunaan yang luas.

Tujuan kami adalah membuat Inery dapat digunakan untuk apa saja dan segalanya. Ini dapat digunakan dalam penyimpanan yang aman, obat-obatan, rantai pasokan, keuangan, perbankan, dll. Aplikasi platform Inery berfungsi sebagai wadah untuk menyimpan data yang terus diubah menjadi bentuk yang dapat dibaca komputer. Dengan cara ini, dengan data yang disimpan dengan aman dan terikat oleh kontrak nilai, Inery Blockchain memungkinkan untuk menyimpan, memvariasikan, dan mentransfer data dengan transparansi dan keamanan maksimal.

Perangkat lunak Inery mewakili solusi sempurna untuk bisnis apa pun yang ingin mendapat manfaat dari teknologi blockchain terdesentralisasi. Dengan demikian, Inery dirancang khusus untuk mengatasi desentralisasi database.

Source :
> [What is Inery](https://docs.inery.io/docs/introduction-1)


# Tutorial Menjalankan Master Node pada Inery Testnet

Dokumen official :
> [Node Lite & Master](https://docs.inery.io/docs/category/lite--master-nodes)

Eksplorer Inary :
> [Explorer Inary](https://explorer.inery.io/ "Explorer Inary")

## Spesifikasi Testnet Inary

> Hardware

|  Komponen |  Persyaratan Minimum |
| ------------ | ------------ |
| CPU  | Intel Core i7-8700 Hexa-Core  |
| RAM | DDR4 64 GB  |
| Penyimpanan  | 2x1 TB NVMe SSD |
| koneksi | Port 1 Gbit/dtk |

> Software

|Komponen | Persyaratan Minimum |
| ------------ | ------------ |
| OS |  Ubuntu 18.04 atau lebih tinggi  | 

## Registrasi Akun Testnet
- Buka Link Registrasi : [Register Inery](https://testnet.inery.io/ "https://testnet.inery.io/")
- Isi Data kalian Seperti di Bawah Ini.
![regist akun1](https://user-images.githubusercontent.com/91620434/192931934-a93ab7ec-1b86-4cdd-acae-502b0a71f925.png)

!!! JANGAN LUPA SIMPAN PHRASE KALIAN!!!

<p align="center">
  
![Screenshot 2022-09-29 103955](https://user-images.githubusercontent.com/91620434/192933434-104818a7-1f2f-4e43-958f-7eab40bf5f9e.png)


## Mendapatkan Nama Server

> VPS Contabo

- Login akun Contabo
- Pilih `Reverse DNS Managamenet`
- Cari IP Address Kalian dan Salin Link PTR Record nya
- Data tersebut merupakan Nama dari Server
- Alamat IP : Isi Dengan Alamat IP VPS
- Nama Akun : Isi Username
- Masukan Password
- Submit Pendaftaran

> VPS Azure

-Sama dengan nama Server saat mendaftar dan sama juga dengan IP Public

## Claim Faucet Inery (Untuk Master Node)


![Screenshot 2022-09-29 103731](https://user-images.githubusercontent.com/91620434/192933115-ab7974d9-09a1-420e-b17a-02ee84eb62bd.png)

- Faucet dapat diambil bebas

## 1. Update Tools Yang di Perlukan

```
sudo apt-get update && sudo apt install git && sudo apt install screen
```

<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/38981255/184288416-3eab98fb-2544-4be8-bae2-f6c99210750d.PNG">
</p>

```
sudo apt-get install -y make bzip2 automake libbz2-dev libssl-dev doxygen graphviz libgmp3-dev \
autotools-dev libicu-dev python2.7 python2.7-dev python3 python3-dev \
autoconf libtool curl zlib1g-dev sudo ruby libusb-1.0-0-dev \
libcurl4-gnutls-dev pkg-config patch llvm-7-dev clang-7 vim-common jq libncurses5
```

## 2. Membuka Port
```
ufw allow 22 && ufw allow 8888 && ufw allow 9010 && ufw enable -y
```

## 3. Memulai Menjalankan Node
```
git clone https://github.com/inery-blockchain/inery-node
```

## 4. Explorer BIN
```
cd inery-node
```

## 5. Beri Izin File

```
cd inery.setup
```
```
chmod +x ine.py
```
```
./ine.py --export
```
```
cd; source .bashrc; cd -
```
## 6. Become a Master Node
Berikut merupakan gambar untuk mengkonfigurasi node dengan informasi akun, Harap diperhatikan dengan teliti karna pada langkah ini dapat menyebabkan error jika ada yang terlewatkan

<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/38981255/184290164-85371bac-f97a-4f8d-8cf8-63e5b5297f83.PNG">
</p>

## 7. Buka Config Kalian Lalu Edit, Perintahnya : 
```
cd inery-node/inery.setup
```
```
cd tools
```
```
nano config.json
```
**Penting:** Untuk Pengguna VPS Azure IP bisa di isi Dengan IP Private Kalian Cari Jalankan Perintah 
```
hostname - i
```

Pastikan Data Sama Dengan [Akun Testnet](https://github.com/bangpateng/inery/blob/main/cara-register-testnet.md "Akun Testnet") Yang ada di Dasboard Akun Yang Sudah Kalian Buat

Simpan (ctrl+x), Ketik "Y" dan keluar (enter)

## 8. Mulai Protocol Blockchain

```
cd inery-node/inery.setup
```
```
screen -R master
```
```
./ine.py --master
```
`Ketik CTRL + A + D`Merupakan perintah untuk kembali ke background dan Untuk Kembali lagi Ke Screen

Untuk kembali ke tampilan screen
```
screen -Rd master
```
<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/38981255/184290965-fd0f6127-d351-4f55-9102-18aa1bbb38c2.PNG">
</p>

-Jika Menunjukan Seperti di Atas, Anda Harus Mengganti Peer di, Gunakan Perintah (Lakukan di TAB Baru)
```
cd inery-node/inery.setup/master.node/
nano genesis_start.sh
```

## 9. Add Peer baru
<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/38981255/184370626-5b3dc227-3800-4140-a9c0-ce5b0b13e1e1.PNG">
</p>

**Isi Seperti Pada Contoh Gambar**

- 62.210.245.223
- 192.99.62.6
- 15.235.133.9

## 10. Masukan Peer
```
--p2p-peer-address 15.235.133.9:9010 \
--p2p-peer-address 147.78.0.168:9010 \
--p2p-peer-address 38.242.229.50:9010 \
--p2p-peer-address sys.blockchain-servers.world:9010 \
--p2p-peer-address bis.blockchain-servers.world:9010 \
--p2p-peer-address 167.235.71.28:9010 \
--p2p-peer-address 62.210.245.223:9010 \
--p2p-peer-address 192.99.62.6:9010 \
--p2p-peer-address 5.199.139.117:9010 \
--p2p-peer-address 151.139.87.56:9010 \
--p2p-peer-address server3.inery.dev:9010 \
--p2p-peer-address 15.235.133.9:9010 \
--p2p-peer-address 5.161.96.50:9010 \
--p2p-peer-address 198.244.241.210:9010 \
--p2p-peer-address 15.235.133.9:9010 \
--p2p-peer-address 147.78.0.168:9010 \
--p2p-peer-address 147.78.3.186:9010 \
```

**Penting :** Peer di Atas, Jika Sudah Tidak Work Kalian Bisa Cari Peer Baru di Discord Group Mereka , Tapi Saat Ini Masih Wangi.

## 11. Restart Node
```
./stop.sh
```

Tunggu Sekitar 5-10 Detik

```
./genesis_start.sh
```

<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/38981255/184370620-b73f5269-50ad-47aa-9b03-d55d8718c614.PNG">
</p>

Jika Sudah Seperti Gambar di Atas, Artinya Sudah jalan dan Tunggu Sampai 1 - 2 Jam Untuk Mensinkronkan (Ngejar Block Yang Ada di Explorer) `JADI KUDU SABAR SIRR..`

<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/38981255/184388159-4b0ebd21-8b4e-4f28-a10f-03b1626db075.PNG">
</p>

Jika Sudah Seperti gambar di atas, Artilnya Sudah Selesai Sinkron, Silahkan Lanjut Next Step

## 12. Start Node
### Lakukan Ini Masih di TAB Baru
```
cd ~/inery-node/inery.setup/master.node/
./start.sh
```
## 13. Daftar dan setujui (Menghubungkan Wallet dengan Dasboard Akun)

### Lakukan Ini Masih di TAB Baru

<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/38981255/184527922-31fd49ff-84f1-4023-8f65-ec53d86ac65c.PNG">
</p>

```
cline wallet create -n <your_name_wallet> -f file.txt
```
file.txt berisi Password Wallet kalian (Kalian membutuhkan itu Jika Wallet kalian dalam Keadaan Lock)
```
cline wallet import --private-key <your_private_key> -n <your_name_wallet>
```
Import Private Key kalian ke Wallet

### Daftar sebagai produser dengan menjalankan perintah:

```
cline system regproducer <your_account> <your_public_key> 0.0.0.0:9010
```
```
cline system makeprod approve <your_account> <your_account>
```
Semua Perintah di atas Jalankan tanpad tanda (<>)

<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/38981255/184528112-8e93070c-a0ba-43d1-b435-92476fa7177c.PNG">
</p>

**Note :** Silahkan Check di Explorer Inery ,Congratss Tutorial Master Node Selesai!!!

# Perintah Berguna 

## Check Saldo Wallet 
```
cline get currency balance inery.token ACCOUNT_NAME
```
## Delete Wallet di Node
```
cline wallet stop
```
```
rm -rf inery-wallet
rm -rf file.txt
rm -rf defaultWallet.txt
```

Save CTRL X lalu Y dan Enter
