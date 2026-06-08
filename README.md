# 🔐 Sistem Autentikasi Password Berbasis Argon2id + Salt

## 📖 Deskripsi Proyek

Proyek ini merupakan implementasi sistem autentikasi berbasis web yang menggunakan algoritma **Argon2id** dan mekanisme **Salt** untuk meningkatkan keamanan penyimpanan password pengguna.

Sistem menyediakan fitur **Registrasi** dan **Login**, di mana password tidak disimpan dalam bentuk asli (*plaintext*), melainkan diubah menjadi nilai **hash** menggunakan pendekatan Argon2id sebelum disimpan.

Tujuan utama proyek ini adalah memahami konsep keamanan password modern, khususnya penggunaan algoritma hashing yang tahan terhadap serangan **Brute Force**, **Rainbow Table**, dan berbagai metode cracking lainnya.

---

## ✨ Fitur Utama

* 🔐 Registrasi pengguna dengan hashing password Argon2id
* 🧂 Salt acak 16-byte untuk setiap pengguna
* 🔄 Verifikasi password melalui proses hashing ulang
* 📊 Password Strength Indicator
* 📜 Process Log real-time
* 💾 Penyimpanan data menggunakan Local Storage
* 👀 Database Viewer untuk melihat data hash dan salt yang tersimpan
* 🚫 Password asli tidak pernah disimpan

---

## 🛡️ Teknologi Keamanan

### Argon2id

Argon2id merupakan algoritma hashing modern yang memenangkan **Password Hashing Competition (PHC) 2015**.

Keunggulan Argon2id:

* Memory-hard hashing
* Tahan terhadap serangan GPU dan ASIC
* Tahan terhadap brute force attack
* Direkomendasikan untuk sistem autentikasi modern

### Salt

Salt adalah data acak yang ditambahkan ke password sebelum proses hashing.

Manfaat penggunaan salt:

* Password yang sama menghasilkan hash berbeda
* Mencegah Rainbow Table Attack
* Meningkatkan keamanan database password

---

## ⚙️ Parameter Hashing

| Parameter          | Nilai                            |
| ------------------ | -------------------------------- |
| Algoritma          | Argon2id (Manual Implementation) |
| Memory Block       | 4096                             |
| Iteration / Passes | 3                                |
| Parallelism        | 1                                |
| Salt Length        | 16 Byte                          |
| Hash Length        | 32 Byte                          |

---

## 🏗️ Struktur Sistem

```text
Pengguna
    │
    ▼
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

### Saat Login

```text
Input Username & Password
    │
    ▼
Ambil Salt dari Database
    │
    ▼
Hash Password Input
    │
    ▼
Bandingkan Hash
    │
    ├── Cocok  → Login Berhasil
    └── Tidak → Login Ditolak
```

---

## 🖥️ Teknologi yang Digunakan

* HTML5
* CSS3
* JavaScript (Vanilla JS)
* Local Storage
* Web Crypto API

---

## 🚀 Cara Menjalankan

1. Clone repository:

```bash
git clone https://github.com/username/argon2-auth.git
```

2. Masuk ke folder proyek:

```bash
cd argon2-auth
```

3. Jalankan file:

```bash
Argon2Final.html
```

atau buka langsung menggunakan browser:

```text
Google Chrome
Microsoft Edge
Firefox
```

---

## 📂 Penyimpanan Data

Saat ini sistem menggunakan:

```javascript
localStorage
```

Data yang disimpan:

```json
{
  "username": {
    "salt": "...",
    "hash": "...",
    "time": "...",
    "params": "mem=4096;pass=3;hashLen=32"
  }
}
```

---

## 🧪 Pengujian Sistem

### Registrasi

✅ Username dan password berhasil disimpan

✅ Salt dibuat otomatis

✅ Hash Argon2id berhasil dibuat

---

### Login

✅ Password benar → Login berhasil

❌ Password salah → Login ditolak

---

### Integritas Data

Perubahan satu karakter password menghasilkan hash yang berbeda secara signifikan.

---

## 📌 Kelebihan Sistem

* Menggunakan konsep keamanan modern
* Password tidak disimpan dalam bentuk plaintext
* Salt unik untuk setiap pengguna
* Tahan terhadap Rainbow Table Attack
* Tampilan interaktif dan edukatif
* Menampilkan proses hashing secara real-time

---

## ⚠️ Keterbatasan

* Implementasi Argon2id masih bersifat manual untuk tujuan pembelajaran
* Belum menggunakan library Argon2 resmi
* Belum memiliki backend server
* Masih menggunakan Local Storage sebagai database sementara
* Belum dirancang untuk penggunaan skala produksi

---

## 🔮 Pengembangan Selanjutnya

Beberapa fitur yang dapat ditambahkan:

* Backend menggunakan Node.js / Express
* Database MySQL atau PostgreSQL
* HTTPS
* JWT Authentication
* Multi-Factor Authentication (MFA)
* One-Time Password (OTP)
* Rate Limiting
* Implementasi Argon2 resmi

---

## 👨‍💻 Tim Pengembang

**Bayu Adhandika** (2401020011)

**Al Adlhu Sodri Niwrad** (2401020015)

**Muhammad Al Fikry Akbar** (2401020031)

Program Studi Teknik Informatika
Fakultas Teknik dan Teknologi Kemaritiman
Universitas Maritim Raja Ali Haji

---

## 📄 Lisensi

Proyek ini dibuat untuk tujuan pembelajaran dan pengembangan akademik.
