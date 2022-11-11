# Tutorial testnet Exorde menggunakan anaconda anti error

## Referensi

[Github resmi Exorde-Labs](https://github.com/exorde-labs/ExordeModuleCLI/)

[Pemasangan Anaconda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html)

[Tutorial by Airdrop Finder](https://github.com/bayy420-999/tutorial-testnet-exorde-airdropfinder/blob/main/README.md)

## Persyaratan perangkat keras

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|CPU|Intel Core i3 or i5|
|RAM|4 GB DDR4 RAM|
|Penyimpanan|500 GB HDD|
|Koneksi|100 Mbit/s port|

| Komponen | Spesifikasi rekomendasi |
|----------|---------------------|
|CPU|Intel Core i7-8700 Hexa-Core|
|RAM|64 GB DDR4 RAM|
|Penyimpanan|2 x 1 TB NVMe SSD|
|Koneksi|1 Gbit/s port|

## Persyaratan perangkat lunak

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|Sistem Operasi|Ubuntu 16.04|

| Komponen | Spesifikasi rekomendasi |
|----------|---------------------|
|Sistem Operasi|Ubuntu 18.04 atau lebih tinggi|


## Pemasangan menggunakan Anaconda

### Pasang dependensi

Jalankan perintah dibawah untuk memasang dependensi pada root

```
apt install python3 python3-pip python3-venv git screen
```
```
pip install --upgrade pip eth-account fasttext-langdetect facebook_scraper geopy iso369
```

### Unduh dan jalankan Anaconda

```
wget https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh
bash Anaconda3-2022.10-Linux-x86_64.sh
bash
```

> Jika ada prompt pertanyaan ketik `yes` sampai proses pemasangan selesai.

> Setelah selesai menginstall anaconda ketik `reboot` lalu `R` untuk merestart vps.

> Selanjutnya masuk ke root dan lanjut ke pengunduhan paket exorde dibawah ini:


### Unduh paket Exorde

```
git clone https://github.com/exorde-labs/ExordeModuleCLI.git
```

### Masuk ke folder Exorde

```
cd ExordeModuleCLI
```

### Buat virtual environment Exorde

```
conda create --name exorde-env python=3.9
```

### Aktifkan virtual enviroment Exorde tadi yang telah dibuat

```
conda activate exorde-env
```

### Pasang dependensi python

```
pip install -r requirements.txt
```

### Jalankan validator

Lalu jalankan perintah dibawah

```
python Launcher.py -m ALAMAT_ETH_ANDA -l LEVEL_LOGGING
```
> Ganti `ALAMAT_ETH_ANDA` dengan alamat eth anda, untuk logging bisa diisi 0, 1, 2, 3, 4 detail logging akan saya jelaskan [dibawah](https://github.com/ilhambyte/tutorial-tesnet-exorde-menggunakan-anaconda#logging)

contoh:

```
python Launcher.py -m 0x2192F0B2323Ae5dD399672724084c8557F85B685 -l 4
```

Jika anda ingin keluar dari terminal tekan 

```CTRL + A + D```

Jika anda ingin masuk ke terminal gunakan perintah 

```
screen -r exorde
```

## Logging

| Logging level | Keterangan |
|---------------|------------|
|0|Tidak ada log|
|1|Log biasa|
|2|Log validasi|
|3|Log validasi dan scrapping|
|4|Log validasi (detail) + log scrapping (untuk troubleshoot)

> Saya menyarankan menggunakan Logging level 4 agar mempermudah troubleshoot jika ada masalah
