# Farhan Fairuz Zamiir — DKV Portfolio

Website portofolio satu halaman (single-page) untuk **Farhan Fairuz Zamiir**, pelajar Desain Komunikasi Visual (DKV) di SMKN 10 Surabaya. Dibangun murni dengan **HTML, CSS, dan JavaScript** tanpa framework, tanpa build tools, dan tanpa dependency eksternal selain Google Fonts serta embed Spotify.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![No Build](https://img.shields.io/badge/build-none-2563eb?style=flat-square)

---

## Daftar Isi

- [Tentang Proyek](#tentang-proyek)
- [Fitur Utama](#fitur-utama)
- [Teknologi](#teknologi)
- [Struktur Proyek](#struktur-proyek)
- [Cara Menjalankan](#cara-menjalankan)
- [Daftar Aset & Penamaan File](#daftar-aset--penamaan-file)
- [Kustomisasi](#kustomisasi)
- [Pintasan & Perintah](#pintasan--perintah)
- [Deployment](#deployment)
- [Catatan Performa](#catatan-performa)
- [Kontak & Hak Cipta](#kontak--hak-cipta)

---

## Tentang Proyek

Portofolio ini menampilkan identitas, karya, pengalaman magang, dan kanal kontak Farhan dalam satu halaman interaktif bertema **luar angkasa / nebula biru gelap**. Semua konten berada di dalam satu file `index.html`:

- **Section Home** — perkenalan, efek mengetik, tombol navigasi, dan ID card 3D dengan tali lanyard.
- **Section About** — profil singkat, foto dengan efek lensa kursor, pendidikan, pengalaman PKL di ITS, statistik, dan playlist Spotify.
- **Section Portfolio** — 4 tab: proyek video & grup foto, sertifikat magang, album, serta design & tools.
- **Section Connect** — terminal interaktif, form pesan WhatsApp, kartu media sosial, dan visitor wall.

---

## Fitur Utama

### 1. Hero & ID Card Interaktif
- **Latar kosmik animasi** (`<canvas>`): 65 node bintang yang saling terhubung garis, bereaksi terhadap posisi kursor, plus sparkle berkedip.
- **Efek typing** yang bergantian menampilkan 3 peran: *Visual Communication Designer*, *Video & Motion Graphic Creator*, *Photography & Brand Identity*.
- **ID card dengan fisika spring**: kartu bisa ditarik dengan mouse/sentuh, tali lanyard (SVG) ikut melengkung mengikuti gerakan.
- **Klik kartu untuk flip** ke sisi belakang yang berisi QR Instagram.
- **Navbar pil mengambang** dengan highlight otomatis sesuai section yang sedang dilihat (scroll spy).

### 2. About Me
- **Efek lensa kursor**: foto utama berlubang melingkar mengikuti kursor dan menampilkan foto kedua di bawahnya.
- **Timeline pendidikan**: SMKN 10 Surabaya (DKV, 2024–2027) dan MTs. Nurul Huda (2021–2024), lengkap dengan logo sekolah.
- **Pengalaman magang**: Departemen Teknik Material dan Metalurgi, FTIRS — ITS (28 Juli – 16 Oktober 2026), nilai akhir 90 (Sangat Baik), nomor sertifikat, dan 3 thumbnail sertifikat.
- **Kartu statistik** yang bisa diklik untuk langsung menuju tab portfolio terkait.
- **Embed Spotify** untuk playlist pribadi.

### 3. Portfolio (4 Tab)
| Tab | Isi |
| --- | --- |
| **Projects (6)** | 3 video (hover untuk preview) + 3 grup foto dengan layout kolase berbeda (16, 2, dan 4 foto) |
| **Certificates & Magang (3)** | 3 lembar sertifikat ITS, termasuk tabel rincian nilai PKL |
| **My Album** | 4 slot album (`album1.jpg` – `album4.jpg`) yang bisa diperbesar |
| **Design & Tools** | Ringkasan keahlian *Graphic Design & Photography* dan *Video Production & Motion* |

- **Lightbox multi-mode** dalam satu modal:
  - mode **video** (diputar langsung di dalam modal),
  - mode **galeri foto** (tombol prev/next, thumbnail strip, navigasi keyboard),
  - mode **sertifikat/album** (rasio A4 landscape dan tombol putar 90°).
- **Placeholder otomatis**: jika file gambar tidak ditemukan, JavaScript menampilkan gambar SVG pengganti berisi nama file yang dibutuhkan, sehingga layout tidak rusak.

### 4. Connect / Command Center
- **Terminal interaktif** dengan perintah `help`, `project`, `magang`, `contact`, dan `clear`, plus jam WIB real-time.
- **Form direct message** yang mengarahkan pesan ke WhatsApp `0881027280328`.
- **Kartu sosial**: Instagram, GitHub, Email, dan WhatsApp.
- **Visitor Wall**: komentar pengunjung disimpan di `localStorage` (key: `farhan_dkv_visitor_wall`), dengan validasi dan escaping HTML.
- **Animasi scroll reveal** (`IntersectionObserver`) untuk elemen saat masuk viewport.

---

## Teknologi

| Bagian | Keterangan |
| --- | --- |
| Markup & styling | HTML5 + CSS3 (inline `<style>`) |
| Interaksi | Vanilla JavaScript (inline `<script>`) |
| Font | [Google Fonts](https://fonts.googleapis.com): Inter, JetBrains Mono, Oswald |
| Ikon | SVG inline (tanpa library ikon) |
| Musik | Spotify Embed iframe |
| Penyimpanan | `localStorage` untuk Visitor Wall |
| Build tools | Tidak ada — cukup buka file HTML |

---

## Struktur Proyek

```text
portofolio/
├── index.html                    # Seluruh website (HTML + CSS + JS)
├── README.md
├── favicon.svg                   # Ikon tab browser (SVG)
├── favicon-32x32.png             # Ikon fallback PNG 32×32
├── apple-touch-icon.png          # Ikon iOS / add to homescreen
├── og-image.jpg                  # Gambar pratinjau tautan 1200×630
├── .nojekyll                     # Menonaktifkan build Jekyll di GitHub Pages
├── .gitignore                    # File yang tidak perlu diunggah
│
├── foto_farhan_bg.jpg            # Foto pada ID card (sisi depan)
├── foto_farhan_nobg.png          # Lapisan atas foto About Me
├── foto_sakamoto.png             # Lapisan reveal saat kursor diarahkan
├── qr_ig.png                     # QR Instagram di belakang ID card
├── logo_smk.png                  # Logo SMKN 10 Surabaya
├── logo_mts.png                  # Logo MTs. Nurul Huda
│
├── video1.mp4                    # Opening Film
├── video2.mp4                    # Effect Hujan
├── video3.mp4                    # Effect Logo
│
├── grup1_1.jpg ... grup1_16.jpg  # Grup foto #1 (16 foto)
├── grup2_1.jpg ... grup2_2.jpg   # Grup foto #2 (2 foto)
├── grup3_1.jpg ... grup3_4.jpg   # Grup foto #3 (4 foto)
│
├── sertifikat_its_depan.jpg      # Sertifikat magang #1
├── sertifikat_its_belakang.jpg   # Transkrip nilai PKL #2
├── sertifikat_its_3.jpg          # Lampiran sertifikat #3
│
└── album1.jpg ... album4.jpg     # Foto tab "My Album"
```

> Semua aset berada di folder yang sama dengan `index.html` dan dipanggil dengan path relatif, jadi pastikan nama file tidak diubah.

---

## Cara Menjalankan

### Opsi 1 — Buka langsung
Klik dua kali `index.html`, atau buka melalui browser. Cara ini paling cepat, tetapi beberapa browser membatasi pemutaran video lokal.

### Opsi 2 — Local server (disarankan)
Jalankan dari folder proyek:

```bash
# Python 3
python -m http.server 8000
```

Lalu buka `http://localhost:8000/` (otomatis memuat `index.html`).

Alternatif:
- Ekstensi **Live Server** di VS Code → *Open with Live Server*.
- `npx serve .` (jika Node.js tersedia).

---

## Daftar Aset & Penamaan File

Jika ingin mengganti konten, gunakan nama file berikut agar otomatis terbaca:

| Kebutuhan | Nama File | Rasio / Catatan |
| --- | --- | --- |
| Foto ID card | `foto_farhan_bg.jpg` | Portrait, disarankan 3:4 |
| Foto About (atas) | `foto_farhan_nobg.png` | Portrait, latar transparan |
| Foto reveal lensa | `foto_sakamoto.png` | Portrait |
| QR Instagram | `qr_ig.png` | 1:1 |
| Logo sekolah | `logo_smk.png`, `logo_mts.png` | 1:1 |
| Video proyek | `video1.mp4`, `video2.mp4`, `video3.mp4` | MP4 (H.264), maks. 1280×720 |
| Grup foto 1 | `grup1_1.jpg` s.d. `grup1_16.jpg` | Bebas, disarankan 16:9 |
| Grup foto 2 | `grup2_1.jpg`, `grup2_2.jpg` | Bebas |
| Grup foto 3 | `grup3_1.jpg` s.d. `grup3_4.jpg` | Bebas |
| Sertifikat | `sertifikat_its_depan.jpg`, `sertifikat_its_belakang.jpg`, `sertifikat_its_3.jpg` | A4 landscape |
| Album | `album1.jpg` s.d. `album4.jpg` | 4:3 |
| Favicon | `favicon.svg`, `favicon-32x32.png` | Ikon tab browser |
| Apple touch icon | `apple-touch-icon.png` | 180×180 |
| Preview tautan | `og-image.jpg` | 1200×630 (Open Graph) |

Sertifikat memakai class rotasi khusus:
- `rot-ccw` — gambar diputar 90° berlawanan arah jarum jam (dipakai sertifikat depan).
- `rot-cw` — gambar diputar 90° searah jarum jam (dipakai transkrip nilai).
- `rot-normal` — tanpa rotasi.

---

## Kustomisasi

### Identitas & Kontak
Cari dan ganti data berikut di `index.html`:

1. **Nama** — judul halaman, hero, ID card, About, terminal, dan footer kartu.
2. **Media sosial** — tautan Instagram (`instagram.com/hnzzsiaome`), GitHub (`github.com/Hansse-hans`), email (`haannnzzmiirr@gmail.com`), dan WhatsApp (`wa.me/62881027280328`).
3. **Nomor WhatsApp** — ubah juga teks nomor pada form direct message dan perintah `contact` di terminal.
4. **Alamat Spotify** — ganti ID playlist pada tautan dan `src` iframe embed.

### Favicon & Pratinjau Tautan
- `favicon.svg` dan `favicon-32x32.png` adalah ikon tab browser. Ganti dengan desain lain menggunakan nama file yang sama, atau sesuaikan `<link rel="icon">` di `<head>`.
- `apple-touch-icon.png` (180×180) dipakai saat situs ditambahkan ke homescreen iPhone/iPad.
- `og-image.jpg` (1200×630) adalah gambar yang muncul saat tautan dibagikan ke WhatsApp, Instagram, Facebook, X, dan LinkedIn.
- Setelah situs punya URL tetap, ganti nilai `og:image` dan `twitter:image` menjadi **URL absolut**, misalnya:

```html
<meta property="og:image" content="https://username.github.io/nama-repo/og-image.jpg">
<meta name="twitter:image" content="https://username.github.io/nama-repo/og-image.jpg">
```

### Galeri Foto
Jumlah foto tiap grup diatur di dua tempat:

```js
const photoGroups = {
    grup1: {
        title: 'Grup Foto #1 — Seri 16 Karya',
        files: Array.from({ length: 16 }, (_, i) => `grup1_${i + 1}.jpg`)
    },
    // ...
};
```

Ubah `length` sesuai jumlah foto. Untuk tampilan kolase di halaman, sesuaikan juga markup `.group-collage-box` (class `layout-2`, `layout-4`, `layout-16`) dan label jumlah foto.

### Visitor Wall
- Data awal ada di array `defaultComments`.
- Data pengunjung disimpan di `localStorage` dengan key `farhan_dkv_visitor_wall`.
- Untuk mereset dari browser: buka DevTools Console, lalu jalankan:

```js
localStorage.removeItem('farhan_dkv_visitor_wall');
location.reload();
```

### Warna, Font, dan Tema
- Warna utama: `#2563eb` / `#3b82f6` (biru), latar `#040712`, teks `#e2e8f0`, aksen `#38bdf8`.
- Font dimuat melalui `@import` Google Fonts di bagian atas `<style>`.
- Efek latar nebula diatur di `.nebula-glow` dan animasi `nebulaPulse`.

### Konten Terminal
Perintah terminal didefinisikan di fungsi `runTerminalCmd()`:

```js
if (cmd === 'help') { /* ... */ }
else if (cmd === 'project') { /* ... */ }
else if (cmd === 'magang' || cmd === 'magang-its') { /* ... */ }
else if (cmd === 'contact') { /* ... */ }
```

Tambahkan cabang baru jika ingin perintah kustom.

---

## Pintasan & Perintah

### Terminal
| Perintah | Fungsi |
| --- | --- |
| `help` | Menampilkan daftar perintah |
| `project` | Ringkasan proyek video dan grup foto |
| `magang` / `magang-its` | Informasi magang PKL di FTIRS ITS |
| `contact` | Menampilkan seluruh kanal kontak |
| `clear` | Membersihkan output terminal |

### Lightbox
| Aksi | Fungsi |
| --- | --- |
| `Esc` | Menutup lightbox |
| `←` / `→` | Pindah foto (saat galeri grup terbuka) |
| Tombol **Putar 90°** | Merotasi gambar sertifikat/album |
| Klik area gelap di luar konten | Menutup lightbox |

---

## Deployment

Website ini statis dan sudah disiapkan untuk GitHub Pages: entry point `index.html`, favicon, meta pratinjau sosial, dan `.nojekyll` sudah tersedia.

### A. Upload lewat web GitHub (tanpa Git)

1. Buat repository baru di GitHub (mis. `portofolio`), biarkan **Public**.
2. Klik **Add file → Upload files**.
3. Seret **seluruh isi folder** `portofolio` (bukan foldernya) ke area upload, lalu **Commit changes**.
4. Masuk **Settings → Pages**.
5. Pada **Build and deployment**, pilih **Source: Deploy from a branch**.
6. Pilih branch **main** dan folder **/ (root)**, lalu **Save**.
7. Tunggu 1–2 menit. Situs tersedia di:

```text
https://USERNAME.github.io/NAMA-REPO/
```

> Batas upload lewat web GitHub adalah **25 MB per file**. Setelah kompresi, file terbesar (`video1.mp4`) hanya ± **5,2 MB**, jadi seluruh aset aman diunggah lewat web.

### B. Upload lewat Git (jika Git terpasang)

```bash
git init
git add .
git commit -m "Initial commit: DKV portfolio"
git branch -M main
git remote add origin https://github.com/USERNAME/NAMA-REPO.git
git push -u origin main
```

Setelah push, aktifkan GitHub Pages seperti langkah A nomor 4–7.

### C. Netlify / Vercel / hosting biasa

- **Netlify / Vercel**: hubungkan repository atau drag-and-drop folder proyek. Tidak perlu build command; entry point `index.html`.
- **Hosting biasa**: upload seluruh isi folder ke `public_html`, lalu akses domainnya.

### D. Setelah situs tayang

1. Buka URL GitHub Pages dan pastikan foto, video, sertifikat, serta QR tampil.
2. Ganti `og:image` dan `twitter:image` di `<head>` dengan URL absolut `og-image.jpg` agar preview WhatsApp/media sosial bekerja.
3. Cek tampilan di ponsel dan desktop.
4. (Opsional) Pasang custom domain melalui **Settings → Pages → Custom domain**.

### Checklist deploy

- [x] `index.html` sebagai halaman utama
- [x] `.nojekyll` untuk menonaktifkan build Jekyll
- [x] Favicon SVG + PNG dan apple-touch-icon
- [x] Meta description, Open Graph, Twitter Card, dan JSON-LD
- [x] `.gitignore`
- [x] Semua aset memakai path relatif dan namanya cocok
- [ ] `og:image` diganti ke URL absolut setelah URL situs diketahui
- [ ] Seluruh aset berhasil ter-upload

> GitHub Pages gratis untuk repository **publik**. Jika repository privat, GitHub Pages memerlukan paket berbayar. Ingat juga bahwa seluruh isi repo publik (termasuk foto, sertifikat, nomor WhatsApp, dan email) dapat diakses siapa saja.

---

## Catatan Performa

- Seluruh aset sudah dikompres: total folder ± **13,4 MB** (sebelumnya ± 51 MB).
- Video sudah di-encode ulang ke H.264 maksimal 720p dengan audio asli: `video1.mp4` ± **5,2 MB** (dari 23,4 MB), `video2.mp4` ± **1,5 MB**, dan `video3.mp4` ± **1,6 MB**.
- Foto `foto_farhan_bg.jpg` sudah dikompres dari 8,7 MB menjadi ± **165 KB** (sisi terpanjang 1400 px). Foto grup dan sertifikat juga sudah diperkecil ke maksimal 1400 px.
- Jika mengganti video/foto di kemudian hari, kompres dulu agar ukuran repo tetap ringan (video: H.264 CRF 23–26, 720p; foto: JPEG kualitas 80–85, sisi terpanjang 1400 px).
- Video preview hanya diputar saat kursor diarahkan (`mouseenter`) dan berhenti saat kursor keluar, sehingga tidak membebani halaman.
- Animasi canvas berjalan terus-menerus; pada perangkat hemat daya, pertimbangkan menurunkan jumlah node/sparkle.
- Embed Spotify dan Google Fonts memerlukan koneksi internet.

---

## Kompatibilitas

- Chrome, Edge, Firefox, dan Safari versi modern.
- Mendukung perangkat sentuh (drag ID card dan lensa foto memakai event `touch`).
- `backdrop-filter`, `mask-image`, dan `aspect-ratio` memerlukan browser yang cukup baru.

---

## Kontak & Hak Cipta

**Farhan Fairuz Zamiir** — Desain Komunikasi Visual

- Instagram: [@hnzzsiaome](https://instagram.com/hnzzsiaome)
- GitHub: [Hansse-hans](https://github.com/Hansse-hans)
- Email: [haannnzzmiirr@gmail.com](mailto:haannnzzmiirr@gmail.com)
- WhatsApp: [0881027280328](https://wa.me/62881027280328)

© 2026 Farhan Fairuz Zamiir. Seluruh karya, foto, video, dan desain dalam portofolio ini merupakan milik pemiliknya. Mohon jangan menggunakan aset tanpa izin.
