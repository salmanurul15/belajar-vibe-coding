# Application Build Plan (ElysiaJS + Drizzle + MySQL)

## 1. Project Initialization & Setup
- Pastikan Bun sudah terinstall di sistem.
- Instalasi dependensi: jalankan `bun install`.
- Konfigurasi file `.env` dengan variabel `DATABASE_URL` (contoh: `DATABASE_URL=mysql://user:password@localhost:3306/db_name`).

## 2. Database Schema (Drizzle)
- Buat file `src/db/schema.ts` dan definisikan tabel (misalnya tabel `users` dengan field `id`, `name`, `email`).
- Gunakan `drizzle-kit` untuk melakukan push/migrate skema ke database MySQL.

## 3. Setup Aplikasi & Koneksi Database
- Pada `src/index.ts`, inisialisasi koneksi Drizzle ORM menggunakan driver `mysql2`.
- Inisialisasi server ElysiaJS dengan port yang sesuai.

## 4. Pembuatan Endpoint API (ElysiaJS)
- Buat route untuk CRUD dasar (misalnya file terpisah `src/routes.ts` atau langsung di `src/index.ts`):
  - `GET /` untuk health check.
  - `GET /users` untuk mendapatkan daftar pengguna dari database.
  - `POST /users` untuk menambahkan pengguna baru ke database.

## 5. Testing
- Jalankan server mode dev dengan `bun run dev`.
- Tes semua endpoint yang telah dibuat untuk memastikan Response & interaksi Database berjalan normal.
