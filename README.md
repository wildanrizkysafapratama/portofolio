# Website Portofolio — Wildan Rizky Safa Pratama

Website portofolio. **Tanpa instalasi apa pun**, tanpa library eksternal. Tinggal buka `index.html`.

---

## Cara membuka

Klik dua kali `index.html` → terbuka di browser.

Atau lewat server lokal (lebih mirip kondisi online):

```bash
cd "D:/PORTFOLIO KARIR/06_Website"
python -m http.server 8899
```

Lalu buka `http://127.0.0.1:8899`

---

## Struktur file

```
06_Website/
├── index.html                                  ← website portofolio utama
├── cv.html                                     ← CV lengkap (bisa dilihat & dicetak)
├── cv-ats.html                                 ← CV versi ATS (teks polos)
├── PANDUAN_HOSTING.html                        ← panduan hosting GitHub Pages (gratis)
├── README.md                                   ← file ini
├── Portofolio_Wildan_Rizky_Safa_Pratama.pdf    ← portofolio 19 halaman
├── CV_Wildan_Rizky_Safa_Pratama.pdf            ← CV 3 halaman
├── CV_ATS_Wildan_Rizky_Safa_Pratama.pdf        ← CV ATS 3 halaman
├── CV_ATS_Wildan_Rizky_Safa_Pratama.txt        ← CV ATS teks mentah
└── assets/
    ├── img/     ← 70 gambar (dikompres & dinamai rapi)
    └── video/   ← 5 video + poster thumbnail
```

### Halaman yang tersedia

| Halaman | Isi |
|---|---|
| `index.html` | Portofolio utama — hero, tentang, keahlian, pengalaman, 5 proyek, prestasi, **unduh CV**, kontak |
| `cv.html` | CV lengkap berwarna — tombol Cetak/PDF, Unduh PDF, dan tautan ke versi ATS |
| `cv-ats.html` | CV versi ATS (plain text) — untuk portal lamaran otomatis |

---

## Isi bagian website

| Bagian | Keterangan |
|---|---|
| Hero | Nama, headline, IPK 3,84, 4 statistik, foto KRTI 2026 |
| Tentang | 4 paragraf + kartu foto profil + kartu Fokus Keahlian |
| Keahlian | 7 kartu: hardware, protokol, platform, sensor, software, regulasi, non-teknis |
| Pengalaman | Timeline 7 entri dengan tanggal presisi |
| Proyek | 5 proyek — KRTI 2026, KIDN 2025, KRTI 2025, KRTMI, Robot Bawah Air (3 generasi) |
| Prestasi | 4 kartu termasuk sertifikasi FASI + **galeri gambar sertifikat asli** + catatan kejujuran |
| **CV** | Kartu unduhan CV Lengkap + CV ATS + Portofolio PDF |
| Kontak | Email, WhatsApp, LinkedIn, lokasi |

---

## Cara mengubah isi

Buka `index.html` dengan Notepad / VS Code. Cari teks yang mau diubah, langsung ganti.

### Menambah foto ke galeri proyek

1. Simpan gambar ke `assets/img/` dengan nama rapi, misal `krtmi-pcb.jpg`
2. Cari proyeknya di `index.html`, tambahkan satu baris di dalam `<div class="gallery">`:

```html
<figure data-cap="Keterangan yang muncul saat gambar diklik">
  <img src="assets/img/krtmi-pcb.jpg" alt="Deskripsi gambar" loading="lazy" />
  <figcaption>Keterangan singkat</figcaption>
</figure>
```

Class tambahan yang tersedia:

| Class | Efek |
|---|---|
| `class="wide"` | Gambar memakai 2 kolom |
| `class="doc"` | Skematik / tabel / diagram — tampil utuh, latar terang, tidak terpotong |
| `class="doc wide"` | Skematik lebar penuh |
| `class="pcb"` | PCB 3D / layout — latar gelap, tampil utuh |
| `class="portrait"` | Foto tegak (rasio tinggi) |

### Menambah video

1. Simpan video ke `assets/video/` + buat poster (thumbnail) dengan nama sama + `-poster.jpg`
2. Tambahkan di dalam `<div class="video-grid">`:

```html
<figure class="vid">
  <video src="assets/video/nama.mp4" poster="assets/video/nama-poster.jpg"
         preload="none" controls playsinline></video>
  <figcaption><b>Video</b>Keterangan video</figcaption>
</figure>
```

`preload="none"` penting — video hanya diunduh saat tombol putar ditekan, jadi halaman tetap ringan.

### Mengubah data di bagian atas (hero)

Cari `<h1>Wildan Rizky<br><span class="grad">Safa Pratama</span></h1>`.
Untuk mengubah angka statistik (6 proyek / 3,84 IPK / 2 prestasi), cari `<div class="stats">`.

### Mengubah logo / nama di navigasi

```html
<a href="#home" class="brand">
  <img class="brand-mark" src="assets/img/avatar-128.jpg" alt="Wildan Rizky Safa Pratama" />
  <span class="brand-name">WILDAN RIZKY SAFA PRATAMA</span>
</a>
```

Ganti `assets/img/avatar-128.jpg` dengan foto lain (disarankan persegi, minimal 128×128 px).

---

## Publikasi ke GitHub Pages (gratis)

Setelah punya akun GitHub:

1. Buat repository baru, misal `portfolio`
2. Upload **isi folder `06_Website`** (semua file + folder `assets`) — bukan foldernya
3. Masuk **Settings → Pages**
4. Bagian *Source*: pilih **Deploy from a branch**
5. Branch: `main`, folder: `/ (root)` → **Save**
6. Tunggu 1–2 menit, alamatnya jadi:
   `https://<username>.github.io/portfolio/`

Alamat itu bisa ditempel ke LinkedIn (bagian **Featured** atau **Contact info → Website**).

---

## Catatan ukuran

| Folder | Ukuran |
|---|---|
| `assets/img` | ± 13 MB (termasuk 3 gambar sertifikat)
| `assets/video` | ± 106 MB ← **paling berat** |

**Untuk GitHub Pages:** total ~129 MB masih di bawah batas, tapi repo akan lambat di-clone.
Saran: pindahkan 2 video besar (47 MB & 45 MB) ke YouTube, lalu ganti tag `<video>` dengan
embed YouTube. Video kecil (2,6 MB & 5,3 MB) boleh tetap lokal.

Aset sumber mentah (120 MB) **tidak** disimpan di sini — dipindah ke
`D:/PORTFOLIO KARIR/02_Proyek/_Sumber_Mentah/NewImg_Asli`.

---

## Regenerasi PDF

Setelah mengubah `index.html` atau `cv.html`, PDF perlu dibuat ulang:

```bash
CH="/c/Program Files/Google/Chrome/Application/chrome.exe"

# portofolio
"$CH" --headless=new --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="Portofolio_Wildan_Rizky_Safa_Pratama.pdf" \
  --virtual-time-budget=15000 "file:///D:/PORTFOLIO%20KARIR/06_Website/index.html"

# CV
"$CH" --headless=new --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="CV_Wildan_Rizky_Safa_Pratama.pdf" \
  --virtual-time-budget=9000 "file:///D:/PORTFOLIO%20KARIR/06_Website/cv.html"

# CV ATS
"$CH" --headless=new --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="CV_ATS_Wildan_Rizky_Safa_Pratama.pdf" \
  --virtual-time-budget=9000 "file:///D:/PORTFOLIO%20KARIR/06_Website/cv-ats.html"
```

Atau minta agen meregenerasi — lebih cepat dan sudah teruji.

---

## Catatan kejujuran isi

| ✅ Ditulis | ❌ Tidak ditulis |
|---|---|
| Electrical Engineer, Head Senior Electric | — |
| Operasi misi otonom: pre-flight check, arming, monitoring, landing | "Menerbangkan drone" / pilot manual |
| Integrasi fisik & daya untuk Jetson dan LiDAR | Integrasi software LiDAR (bidang program) |
| Konfigurasi drone via Mission Planner (2025) | Konfigurasi waypoint misi |
| Desain 3D ditandai sebagai karya tim mekanik | Mengklaim desain 3D sebagai milik sendiri |
| Sertifikasi FASI (bukan Kemenhub) | "Sertifikasi pilot drone Kemenhub" |

**Jangan menambahkan klaim di atas batas ini.** Kalau ditanya saat wawancara dan tidak bisa
menjelaskan, kredibilitas justru turun.

---

## Yang masih perlu dilengkapi

- [x] Dokumentasi visual proyek **Robot Tematik KRTMI** — Master V1/V2, Slave, 3 foto robot, 2 video
- [x] Sertifikasi drone — FASI, ID 20260936-JRPFASI
- [x] CV & CV ATS bisa diunduh pengunjung
- [ ] Foto close-up GPS RTK & wiring ke Orange Cube
- [ ] Foto diri sedang bekerja (solder / pegang PCB / di lapangan)
- [ ] Pindahkan 2 video besar ke YouTube agar repo ringan
