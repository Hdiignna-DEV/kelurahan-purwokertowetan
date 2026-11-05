# Panduan Deploy ke Vercel (Gratis, Tanpa Server/Database)

Website berjalan dalam **mode lokal**: semua data (pengumuman, hari besar, berita, dll.) disimpan di
**localStorage browser**. Tidak perlu server, database, atau kunci apa pun.

> Catatan mode lokal: data yang diubah admin hanya tersimpan di browser/perangkat admin itu sendiri,
> tidak terbagi ke perangkat warga lain. Cocok untuk demo/tugas. Data awal ada di `frontend/src/lib/local/seed.json`.

## Langkah 1 — Upload ke GitHub
1. Ekstrak zip.
2. Buka https://github.com/new → buat repo (mis. `website-kelurahan-purwokerto-wetan`).
3. Klik **uploading an existing file** → seret **isi** folder hasil ekstrak (folder `frontend`, file `vercel.json`, `README.md`, dll.).
   Pastikan `vercel.json` ada langsung di halaman utama repo → **Commit changes**.

## Langkah 2 — Deploy di Vercel
1. https://vercel.com/signup → **Continue with GitHub** (paket Hobby/gratis).
2. **Add New… → Project** → pilih repo → **Import**.
3. Framework Preset: `Other`, Root Directory: `./`. Tidak perlu Environment Variables.
4. Klik **Deploy**, tunggu ±3 menit → buka `https://nama-proyek.vercel.app`.

## Langkah 3 — Cek
- Admin: `/admin/login` → username `admin`, kata sandi `Admin#PWetan2026` (segera ganti di menu profil).
- Pengumuman: buat di admin → tampil di beranda & popup (di browser yang sama).
- Hari Besar: otomatis dari kalender libur nasional. Uji tanggal tertentu: `/?simulasi_tanggal=2026-08-17`.

## Masalah umum
| Gejala | Solusi |
|---|---|
| 404 saat refresh halaman | Pastikan `vercel.json` ada di halaman utama repo. |
| Build gagal | Pastikan folder `frontend` lengkap beserta `yarn.lock`. |
| Data hilang | Data mode lokal terhapus jika cache/data situs browser dibersihkan. |

Folder `backend/` disertakan sebagai opsi (FastAPI + MongoDB) bila suatu saat ingin data bersama; tidak dipakai di mode lokal.
