# 📦 Simple LMS (Django + PostgreSQL + Docker)

Project ini merupakan aplikasi Django sederhana yang dijalankan menggunakan Docker dan menggunakan PostgreSQL sebagai database. Project ini dibuat untuk memenuhi tugas dengan kriteria Docker, Django, PostgreSQL, dan dokumentasi yang lengkap.

---

## 🚀 Cara Menjalankan Project

Ikuti langkah-langkah berikut untuk menjalankan project dari awal:

### 1. Clone repository

```bash
git clone (https://github.com/hafizh1119/Simple-LMS---Docker-Django-Foundation)
cd simple-lms
```

---

### 2. Copy file environment

```bash
copy .env.example .env
```

---

### 3. Build dan jalankan Docker

```bash
docker-compose up --build
```

👉 Tunggu sampai proses build selesai dan container berjalan.

---

### 4. Jalankan migrasi database

Buka terminal baru, lalu jalankan:

```bash
docker-compose exec web python manage.py migrate
```

👉 Perintah ini digunakan untuk membuat tabel database di PostgreSQL.

---

### 5. Buat superuser (admin)

```bash
docker-compose exec web python manage.py createsuperuser
```

Isi:

* Username
* Email
* Password

---

### 6. Akses aplikasi

* 🌐 Website: http://localhost:8000
* 🔐 Admin: http://localhost:8000/admin

---

## 🔐 Environment Variables

Project ini menggunakan file `.env` untuk konfigurasi aplikasi dan database.

### 📄 Contoh `.env.example`

```env
DEBUG=True
SECRET_KEY=your-secret-key

POSTGRES_DB=lms_db
POSTGRES_USER=lms_user
POSTGRES_PASSWORD=lms_pass
POSTGRES_HOST=db
POSTGRES_PORT=5432
```

---

### 📌 Penjelasan Variabel

| Variable          | Penjelasan                                         |
| ----------------- | -------------------------------------------------- |
| DEBUG             | Mengaktifkan mode development                      |
| SECRET_KEY        | Kunci rahasia Django                               |
| POSTGRES_DB       | Nama database PostgreSQL                           |
| POSTGRES_USER     | Username database                                  |
| POSTGRES_PASSWORD | Password database                                  |
| POSTGRES_HOST     | Host database (menggunakan service `db` di Docker) |
| POSTGRES_PORT     | Port database PostgreSQL                           |

---

## 🐳 Docker Services

Project ini menggunakan Docker Compose dengan dua service utama:

### 1. Web (Django)

* Menjalankan aplikasi Django menggunakan Gunicorn
* Port: 8000

### 2. Database (PostgreSQL)

* Menyimpan data aplikasi
* Port: 5432

---

## 📸 Screenshot

### ✅ 1. Django Welcome Page

Menampilkan bahwa aplikasi Django berhasil berjalan.

![Django](Dokumentasi/django.png)

---

### ✅ 2. Admin Login Page

Menampilkan halaman login admin Django.

![login](Dokumentasi/login.png)

---

### ✅ 3. Admin Dashboard

Menampilkan dashboard setelah login sebagai admin.

![Admin](Dokumentasi/dashboard.png)

---

### 🐳 4. Docker Running

Menampilkan container Docker yang sedang berjalan.

![Docker](Dokumentasi/docker.png)

---

## 📁 Project Structure

```bash
simple-lms/
├── docker-compose.yml
├── Dockerfile
├── .env.example
├── requirements.txt
├── manage.py
├── config/
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── README.md
```
