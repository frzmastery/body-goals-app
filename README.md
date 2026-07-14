# Ledger — Body Goals Tracker

Aplikasi pelacak body goals: berat badan, target defisit/surplus kalori, catatan makan + kalori/makro, olahraga (lari, jalan kaki, kekuatan, dll). Dibangun dengan Next.js + Tailwind, seluruh data tersimpan di **localStorage** browser (privat di perangkat masing-masing pengguna, tanpa server/database).

## Fitur

- **Onboarding**: hitung BMR/TDEE (rumus Mifflin-St Jeor) dan target kalori harian otomatis berdasarkan tujuan (turun/naik/jaga berat badan) dan laju perubahan berat per minggu.
- **Ringkasan harian**: ring kalori bergaya "tally", makro (protein/karbo/lemak), navigasi antar tanggal.
- **Catat makanan**: cari dari database makanan lokal Indonesia (nasi, ayam, sate, dll) atau tambah makanan custom, per waktu makan (sarapan/siang/malam/camilan), porsi bisa disesuaikan.
- **Catat aktivitas**: lari, jalan kaki, latihan kekuatan, bersepeda, renang, yoga, HIIT — kalori terbakar dihitung otomatis dari MET x berat badan x durasi.
- **Berat badan**: catat berat berkala + grafik tren menuju target.
- **Profil**: ubah data diri & target kapan saja, kalkulasi otomatis menyesuaikan.

## Menjalankan secara lokal

```bash
npm install
npm run dev
```

Buka http://localhost:3000

## Deploy ke Vercel

**Opsi 1 — via GitHub (disarankan)**
1. Push folder ini ke repository GitHub baru.
2. Buka https://vercel.com/new, pilih repo tersebut.
3. Framework preset otomatis terdeteksi sebagai **Next.js** — tidak perlu ubah konfigurasi apa pun.
4. Klik **Deploy**.

**Opsi 2 — via Vercel CLI**
```bash
npm install -g vercel
vercel login
vercel        # deploy preview
vercel --prod # deploy production
```

Tidak ada environment variable atau database yang perlu disiapkan — aplikasi ini 100% client-side.

## Catatan

- Data disimpan di `localStorage` browser pengguna. Jika pengguna berpindah perangkat/browser atau membersihkan cache, data akan hilang. Untuk versi berikutnya, pertimbangkan menambah autentikasi + database (mis. Vercel Postgres / Supabase) agar data tersinkron lintas perangkat.
- Nilai kalori makanan pada database lokal adalah estimasi, bukan data laboratorium — cocok untuk pelacakan harian umum, bukan medis.
