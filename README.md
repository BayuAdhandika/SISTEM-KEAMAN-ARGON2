# 🔐 Sistem Autentikasi Password Berbasis Argon2id Manual

## 📖 Deskripsi

Proyek ini merupakan implementasi sistem autentikasi berbasis web yang menerapkan algoritma **Argon2id** secara manual menggunakan JavaScript. Sistem dirancang untuk mengamankan password pengguna dengan teknik **hashing** dan **salt unik** pada setiap akun.

Password tidak disimpan dalam bentuk asli (*plaintext*), melainkan diubah menjadi nilai hash sebelum disimpan. Saat proses login, password yang dimasukkan pengguna akan di-hash kembali dan dibandingkan dengan hash yang tersimpan.

Proyek ini dibuat untuk tujuan pembelajaran dan pemahaman konsep keamanan password modern, khususnya implementasi hashing berbasis Argon2id.

---

## ✨ Fitur Utama

* Registrasi pengguna
* Login dan verifikasi password
* Implementasi Argon2id secara manual menggunakan JavaScript
* Salt unik untuk setiap pengguna
* Password Strength Indicator
* Process Log untuk menampilkan proses hashing
* Database Viewer
* Penyimpanan data menggunakan Local Storage
* Password asli tidak pernah disimpan

---

## 🛡️ Konsep Keamanan

### Hashing Password

Password pengguna diproses menggunakan algoritma hashing sehingga tidak dapat dikembalikan ke bentuk aslinya.

### Salt

Setiap password diberikan salt acak sebelum proses hashing.

Manfaat penggunaan salt:

* Menghasilkan hash yang berbeda untuk password yang sama
* Mencegah Rainbow Table Attack
* Meningkatkan keamanan data pengguna

### Argon2id

Argon2id merupakan algoritma hashing modern yang dirancang untuk:

* Tahan terhadap brute force attack
* Menggunakan pendekatan memory-hard
* Meningkatkan biaya komputasi bagi penyerang
* Menjadi salah satu standar hashing password modern

---

## ⚙️ Parameter Implementasi

| Parameter           | Nilai   |
| ------------------- | ------- |
| Memory Blocks       | 4096    |
| Passes / Iterations | 3       |
| Lanes               | 1       |
| Hash Length         | 32 Byte |
| Salt Length         | 16 Byte |

---

## 🏗️ Alur Sistem

### Registrasi

```text
Input Username & Password
        │
        ▼
Generate Salt Acak
        │
        ▼
Password + Salt
        │
        ▼
Hashing Argon2id
        │
        ▼
Simpan Hash & Salt
```

### Login

```text
Input Username & Password
        │
        ▼
Ambil Salt Tersimpan
        │
        ▼
Hashing Ulang Password
        │
        ▼
Bandingkan Hash
        │
 ┌──────┴──────┐
 ▼             ▼
Berhasil     Gagal
```

---

## 🖥️ Teknologi yang Digunakan

* HTML5
* CSS3
* JavaScript (Vanilla JS)
* Local Storage
* Implementasi Manual Argon2id
* Browser Crypto API (`crypto.getRandomValues`) untuk pembangkitan salt

---

## 📂 Struktur Data

Data pengguna disimpan pada Local Storage dengan format:

```json
{
  "username": {
    "salt": "salt_hex",
    "hash": "hash_argon2id",
    "time": "tanggal_waktu",
    "params": "mem=4096;pass=3;hashLen=32"
  }
}
```

---

## 🚀 Cara Menjalankan

1. Download atau clone repository.

```bash
git clone https://github.com/username/argon2-auth.git
```

2. Masuk ke folder proyek.

```bash
cd argon2-auth
```

3. Buka file:

```text
index.html
```

4. Jalankan menggunakan browser:

* Google Chrome
* Microsoft Edge
* Mozilla Firefox

---

## 🧪 Pengujian

### Login

| Kondisi                  | Hasil          |
| ------------------------ | -------------- |
| Password benar           | Login berhasil |
| Password salah           | Login ditolak  |
| Username tidak ditemukan | Login ditolak  |

### Integritas Hash

Perubahan satu karakter pada password menghasilkan hash yang berbeda secara signifikan.

### Ketahanan Dasar

Sistem dirancang untuk memberikan perlindungan terhadap:

* Brute Force Attack
* Rainbow Table Attack
* Kebocoran database password

---

## 📌 Kelebihan

* Implementasi hashing dilakukan secara manual
* Password tidak disimpan dalam bentuk plaintext
* Menggunakan salt unik untuk setiap pengguna
* Tampilan interaktif dan informatif
* Menampilkan proses hashing secara real-time
* Cocok sebagai media pembelajaran keamanan password

---

## ⚠️ Keterbatasan

* Belum menggunakan library Argon2 resmi
* Implementasi masih bersifat edukatif
* Menggunakan Local Storage sebagai penyimpanan data
* Belum memiliki backend server
* Belum dirancang untuk lingkungan produksi

---

## 🔮 Pengembangan Selanjutnya

Beberapa pengembangan yang dapat dilakukan:

* Integrasi backend menggunakan Node.js atau PHP
* Database MySQL atau PostgreSQL
* HTTPS
* JWT Authentication
* Multi-Factor Authentication (MFA)
* One-Time Password (OTP)
* Rate Limiting
* Implementasi Argon2 resmi sesuai standar industri

---

## 👨‍💻 Pengembang

**Bayu Adhandika**
**Al Adlhu Sodri Niwrad**
**Muhammad Al Fikry Akbar**

Program Studi Teknik Informatika
Fakultas Teknik dan Teknologi Kemaritiman
Universitas Maritim Raja Ali Haji

---

## 📄 Lisensi

Proyek ini dibuat untuk tujuan pembelajaran, penelitian, dan pengembangan akademik.
