# Website Resmi Kelurahan Purwokerto Wetan

Website profil + layanan Kelurahan Purwokerto Wetan, Kec. Purwokerto Timur, Kab. Banyumas.
**React** (frontend/) dengan data di **localStorage browser** (mode lokal, tanpa server). Backend FastAPI + MongoDB (backend/) opsional.

**Cara online gratis di Vercel: baca [DEPLOY_VERCEL.md](DEPLOY_VERCEL.md).**

## Struktur
```
backend/            FastAPI: API, data awal (seed), unggahan berkas → MongoDB GridFS
frontend/           React (CRA + craco + Tailwind + shadcn/ui)
vercel.json         pengaturan build & routing Vercel
```

## Fitur utama
- Profil, pemerintahan, data & statistik, layanan + lacak permohonan, potensi & UMKM, berita, galeri, partisipasi warga & pengaduan, kontak.
- Panel admin (/admin): konten, kotak masuk permohonan/pengaduan/kiriman, akun & peran, pengaturan situs, riwayat aktivitas.
- **Pengumuman**: tampil di beranda (terbaru di atas) dan popup sekali per kunjungan, dengan masa berlaku.
- **Hari Besar otomatis**: libur nasional & cuti bersama dari kalender resmi (gratis, tanpa kunci), hari peringatan,
  dan hari besar lokal buatan admin. Tampil hari-H s.d. H+2 (WIB) sebagai popup + banner beranda.
  Uji tampilan tanggal tertentu: `?simulasi_tanggal=2026-08-17`.

## Akun admin
Mode lokal: username `admin`, kata sandi `Admin#PWetan2026` (dibuat otomatis).

## Mode data
`REACT_APP_DATA_MODE=local` di `frontend/.env` → data hanya di localStorage browser (tidak terbagi antar perangkat).
Default: mode lokal. Mode server: `REACT_APP_DATA_MODE=backend`.
