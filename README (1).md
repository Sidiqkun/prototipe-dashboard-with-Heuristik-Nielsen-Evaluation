# Dashboard Visualisasi Data Interaktif: Profil Universitas Bengkulu

Prototipe skripsi **"Perancangan Dashboard Visualisasi Data Interaktif Berbasis User-Centered Design dengan Evaluasi Heuristik Nielsen (Studi Kasus: Profil Universitas Bengkulu)"**.

> **Penting:** data di `index.html` adalah **data contoh**. Ganti objek `DATA` dengan data resmi (PDDikti / Biro Akademik UNIB) sebelum dipakai untuk penelitian.

## Cara Pakai
1. Buka `index.html` di browser (butuh internet untuk memuat Chart.js dari CDN).
2. Pilih fakultas dan tahun, klik batang grafik untuk rincian, urutkan tabel, unduh CSV.

## Deploy ke GitHub Pages
```bash
git init
git add .
git commit -m "Prototype dashboard profil UNIB"
git branch -M main
git remote add origin https://github.com/<username>/unib-dashboard.git
git push -u origin main
```
Lalu di GitHub: **Settings → Pages → Branch: main / (root) → Save**.

## Mengganti Data
Edit bagian `DATA` dan `YEARS` pada `index.html`:
```js
{n:"Teknik", m:[2600,2700,2800,2880,2960], d:110, p:7}
// n = nama fakultas, m = mahasiswa per tahun, d = dosen, p = jumlah prodi
```

## Persona (contoh)
**Rina, 38, staf humas/penjaminan mutu.** *Goals:* melihat ringkasan profil kampus dalam 5 detik untuk rapat. *Pain points:* data tersebar di tabel panjang, sulit dibandingkan antar fakultas. *Behavior:* membuka lewat laptop/tablet, sering mengunduh data untuk laporan.

**Skenario:** (konteks) rapat pimpinan mendadak → (trigger) butuh data mahasiswa per fakultas → (aksi) filter tahun, klik fakultas → (hasil) rincian dan CSV siap dilampirkan.

## Penerapan Prinsip Visualisasi
| Prinsip | Implementasi |
|---|---|
| Overview first | Kartu KPI dan grafik seluruh UNIB tampil di awal |
| Zoom and filter | Filter fakultas dan tahun |
| Details on demand | Tooltip, klik batang, panel rincian |
| Pemilihan grafik | Line untuk tren, bar untuk perbandingan kategori |
| Data-ink ratio | Tanpa efek 3D, tanpa legenda berlebihan |
| Aksesibilitas | Kontras tinggi, mode gelap, ARIA, navigasi keyboard |

## Pemetaan 10 Heuristik Nielsen (untuk bahan evaluasi)
| # | Heuristik | Implementasi |
|---|---|---|
| 1 | Visibility of system status | Pesan status setelah setiap aksi |
| 2 | Match with real world | Bahasa Indonesia, istilah akademik umum |
| 3 | User control and freedom | Tombol **Atur ulang filter** |
| 4 | Consistency and standards | Kontrol standar, warna konsisten |
| 5 | Error prevention | Pilihan lewat dropdown, tidak ada input bebas |
| 6 | Recognition over recall | Filter selalu terlihat, fakultas yang dipilih ditandai |
| 7 | Flexibility and efficiency | Klik grafik, sorting tabel, navigasi keyboard |
| 8 | Aesthetic and minimalist | Hanya 2 grafik, 1 tabel, 4 KPI |
| 9 | Recover from errors | Reset filter satu klik |
| 10 | Help and documentation | Tombol **Bantuan** |

## Langkah Evaluasi untuk Skripsi
1. **Heuristic evaluation:** 3 sampai 5 evaluator menilai tiap heuristik (skala severity 0 sampai 4).
2. **Usability testing:** 5 sampai 10 pengguna mengerjakan tugas, misalnya "Temukan jumlah mahasiswa Teknik 2024", "Unduh data 2025". Catat success rate dan waktu.
3. Perbaiki temuan, lalu uji ulang (siklus iteratif UCD).

## Teknologi
HTML, CSS, JavaScript murni + [Chart.js](https://www.chartjs.org/) 4.4.1.
