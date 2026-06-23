# 🐳 Simple LMS - Progress 1 (Django + Docker + PostgreSQL)

Project ini merupakan implementasi **Progress 1: Simple LMS**, yang berfokus pada setup environment menggunakan Docker dan Django.

---

## 🎯 Cara Menjalankan Project

Jalankan perintah berikut:

```bash
docker compose up -d --build

Setelah container berjalan, lakukan migrasi database:
docker compose exec web python manage.py migrate

(Optional) Buat admin user:
docker compose exec web python manage.py createsuperuser

🚀 Akses Aplikasi
Django Home:
http://localhost:8000
Django Admin:
http://localhost:8000/admin

Dokumentasi 
screenshoots/homedjango.png

⚙️Environment Variables

Konfigurasi database menggunakan .env:

DB_NAME=django_db
DB_USER=postgres
DB_PASSWORD=postgres123
DB_HOST=db
DB_PORT=5432

📌 Penjelasan Sistem
🔹 Kenapa perlu volume untuk database?

Volume digunakan agar data database tidak hilang ketika container dihentikan atau dihapus.

🔹 Apa fungsi depends_on?

depends_on memastikan urutan startup container, misalnya database dijalankan terlebih dahulu sebelum web service Django.

🔹 Bagaimana Django container connect ke PostgreSQL?

Django terhubung ke PostgreSQL menggunakan environment variable:

DB_HOST = db (nama service di docker-compose)
Bukan localhost

Karena semua container berada dalam satu Docker network.

🔹 Keuntungan Redis (konsep umum caching)

Redis digunakan untuk:

a. mempercepat response aplikasi
b. mengurangi beban database
c. meningkatkan performa sistem

🧱 Tech Stack
Django
PostgreSQL
Docker
Docker Compose

📦 Status Project

✔ Docker setup complete
✔ Django running
✔ PostgreSQL connected
✔ Admin panel active

👨‍💻 Author

Simple LMS - Progress 1 Assignment
SYAHRATU ANDHARA SATRIANI /A11.2023.14934