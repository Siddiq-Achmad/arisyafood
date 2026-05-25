# PT ARISYAFOOD GLOBAL NIAGA — B2B Export Platform
> Modern, Premium, and Responsive B2B Web Platform Built with Astro & Tailwind CSS v4 utilizing Atomic Design Principles.

---

## 📌 Pendahuluan

Dokumentasi ini mencakup arsitektur proyek, panduan pengembangan, dan spesifikasi sistem desain untuk website **PT ARISYAFOOD GLOBAL NIAGA**. Platform ini dikembangkan khusus untuk memproyeksikan citra perusahaan ekspor agrikultur dan produk pangan Indonesia yang andal, berkualitas premium, dan memenuhi standar higienis internasional kepada pembeli B2B global.

---

## 🛠️ Stack Teknologi (Tech Stack)

Situs ini dibangun menggunakan teknologi mutakhir industri web untuk performa, kemudahan pemeliharaan, dan keramahan SEO:

1. **Astro v6 (Framework Core):** Dipilih karena menggunakan arsitektur *Islands Architecture* yang menghasilkan *zero-JavaScript* secara default untuk kecepatan loading maksimal.
2. **Tailwind CSS v4 (Styling Engine):** Menggunakan versi terbaru Tailwind CSS yang berbasis compiler kilat Vite, mendefinisikan konfigurasi tema `@theme` langsung dalam CSS tanpa perlu file konfigurasi JavaScript terpisah.
3. **TypeScript:** Menjamin integritas tipe data dan keandalan kode di seluruh komponen Astro.
4. **Google Material Symbols (Icons):** Menggunakan ikon berbasis web modern dengan visual modern dan minimalis.

---

## 📂 Arsitektur Kode: Atomic Design

Repositori diatur secara terstruktur menggunakan metodologi **Atomic Design** untuk menjamin modularitas, reusabilitas, dan fleksibilitas komponen:

```
src/
├── components/
│   ├── atoms/         # Komponen dasar yang tidak dapat dipecah lagi
│   ├── molecules/     # Gabungan beberapa atoms membentuk komponen menengah
│   ├── organisms/     # Komponen kompleks siap pakai yang mandiri
│   └── templates/     # Tata letak global/struktur pembungkus halaman
├── pages/             # Rute halaman (Routing Astro berbasis file)
└── styles/            # Gaya global dan kustomisasi tema Tailwind CSS v4
```

### Rincian Komponen:

| Tingkatan (Level) | Komponen | Deskripsi & Kegunaan |
| :--- | :--- | :--- |
| **Atoms** | `Button.astro` | Tombol interaktif dengan varian `primary`, `secondary`, `outline`, dan `text`. |
| | `Badge.astro` | Label penanda status kepatuhan hukum atau kategori sertifikasi. |
| | `Icon.astro` | Wrapper ikon untuk *Google Material Symbols* dengan fitur dinamis (ukuran, fill, weight). |
| | `Logo.astro` | Logo vektor SVG PT ARISYAFOOD GLOBAL NIAGA yang tajam dan responsif. |
| **Molecules** | `ProductCard.astro` | Kartu produk interaktif yang menampilkan gambar, judul, deskripsi, serta tautan aksi cepat. |
| | `ReachItem.astro` | Indikator statistik destinasi ekspor untuk visualisasi jangkauan global. |
| **Organisms** | `Navbar.astro` | Navigasi atas responsif yang dilengkapi dengan deteksi halaman aktif dan menu laci seluler (*mobile drawer*). |
| | `Footer.astro` | Kaki halaman komprehensif berisi peta situs, informasi hak cipta, dan kontak hukum perusahaan. |
| | `ProductCarousel.astro` | Slider/carousel responsif yang menampilkan jajaran produk unggulan perusahaan secara dinamis. |
| | `ReachMap.astro` | Peta interaktif jangkauan ekspor global lengkap dengan grafik statistik pencapaian. |
| | `CertificationBar.astro` | Barisan logo sertifikasi resmi (Halal, ISO 22000, HACCP, BPOM) dengan efek hover berwarna. |
| **Templates** | `MainLayout.astro` | Struktur HTML utama yang menyematkan metadata SEO, integrasi Google Fonts, dan script animasi gulir global. |

---

## 🎨 Sistem Desain (Design System)

Sistem desain ini dirancang untuk merepresentasikan **Keandalan, Kualitas Premium, dan Warisan Nusantara**.

### 1. Palet Warna (Color Palette)
Didefinisikan secara deklaratif di bawah direktori `@theme` di dalam file `src/styles/global.css`:

*   🟢 **Primary (`--color-primary` / `#012d1d` - Deep Forest Green):** Merepresentasikan lanskap alam Indonesia yang subur. Digunakan untuk header, menu navigasi, tombol utama, dan elemen penegasan brand.
*   🟡 **Secondary (`--color-secondary` / `#7a590d` - Harvest Gold):** Terinspirasi dari bulir padi/pangan pada logo. Berperan sebagai aksen prestisius untuk penyorot (highlights), ikon, dan ajakan bertindak (Call to Actions).
*   🟤 **Tertiary (`--color-tertiary` / `#322319` - Earthy Brown):** Memberikan kesan organik dan natural pada elemen latar belakang sekunder, border, atau teks pendukung.
*   ⚪ **Neutral Backgrounds (`--color-background` / `#f8f9fa`):** Memberikan ruang baca yang lapang, bersih, higienis, dan kontemporer.

### 2. Tipografi (Typography)
*   **Font Utama:** **Urbanist** (diintegrasikan melalui Google Fonts).
*   **Karakter:** Geometris, bersih, modern, dan sangat mudah dibaca baik untuk teks kecil logistik maupun judul besar korporat.
*   **Skala Ukuran Teks:**
    - `display-lg`: `48px` (Judul Hero Utama)
    - `headline-lg`: `32px` (Judul Bagian/Section)
    - `headline-md`: `24px` (Judul Komponen/Card)
    - `body-lg`: `18px` (Paragraf Pengantar)
    - `body-md`: `16px` (Teks Utama/Konten)
    - `label-md`: `14px` (Teks Teknis/Logistik dengan spasi huruf `0.05em`)

### 3. Sudut Melengkung (Shapes / Border Radius)
*   `rounded-DEFAULT` (`8px` / `0.5rem`): Digunakan pada tombol, badge, dan kolom input form.
*   `rounded-lg` (`16px` / `1rem`): Digunakan pada kartu produk, panel interaktif, dan bingkai media.
*   `rounded-full` (`9999px`): Digunakan untuk tombol lingkaran penuh atau ikon.

---

## 🚀 Panduan Menjalankan Proyek (Developer Guide)

Pastikan Anda telah menginstal **Node.js** (versi 18 ke atas) di perangkat Anda.

### 1. Instalasi Dependensi
Jalankan perintah berikut di terminal root proyek untuk menginstal seluruh dependensi Astro dan Tailwind CSS:
```bash
npm install
```

### 2. Menjalankan Server Pengembangan (Local Development)
Untuk menjalankan situs secara lokal dengan fitur *Hot Module Replacement* (HMR):
```bash
npm run dev
```
Buka browser Anda dan akses halaman di `http://localhost:4321`.

### 3. Melakukan Build untuk Produksi
Untuk mengompilasi seluruh halaman Astro menjadi file HTML, CSS, dan JS statis yang dioptimalkan penuh untuk produksi:
```bash
npm run build
```
Hasil kompilasi akan berada di dalam direktori `dist/` dan siap diunggah ke penyedia hosting statis.

### 4. Menguji Hasil Build (Preview Mode)
Untuk menguji performa situs web produksi yang telah di-build secara lokal sebelum melakukan deployment:
```bash
npm run preview
```

---

## 🌐 Struktur Rute Halaman (Pages Routing)

Sistem routing Astro berbasis file memetakan setiap file `.astro` di dalam `src/pages/` menjadi halaman publik:

| File Sumber | URL Publik | Fungsi Halaman |
| :--- | :--- | :--- |
| `src/pages/index.astro` | `/` | Beranda Utama PT ARISYAFOOD GLOBAL NIAGA |
| `src/pages/about.astro` | `/about` | Profil Perusahaan, Visi, Misi, & Struktur Nilai |
| `src/pages/products.astro` | `/products` | Katalog Produk Interaktif & Formulir Permintaan B2B |
| `src/pages/legality.astro` | `/legality` | Halaman Legalitas, Kepatuhan, & Sertifikat Mutu |
| `src/pages/gallery.astro` | `/gallery` | Galeri Foto Fasilitas Produksi & Kegiatan Ekspor |
| `src/pages/contact.astro` | `/contact` | Kontak Hubungi Kami, Lokasi Kantor, & Detail Enkuiri |
| `src/pages/privacy.astro` | `/privacy` | Kebijakan Privasi Data untuk Klien Global |
| `src/pages/terms.astro` | `/terms` | Syarat, Ketentuan Transaksi, & Ketentuan Hukum Ekspor |
| `src/pages/cookies.astro` | `/cookies` | Kebijakan Cookie & Pilihan Pengaturan Preferensi |

---

## ✨ Fitur Interaktivitas & Animasi Kustom

Situs web ini menerapkan teknik interaksi modern untuk meningkatkan keterlibatan pengguna tanpa membebani ukuran halaman:

1. **Parallax Scrolling:**
   Gambar latar belakang pada bagian hero banner menggunakan efek paralaks halus yang bergeser secara proporsional saat halaman digulirkan (`id="hero-parallax"`), memberikan kedalaman visual yang premium.
2. **Scroll Reveal Animation:**
   Elemen dengan kelas `.reveal` atau `.reveal-text` secara otomatis akan memudar dan bergeser ke atas secara anggun sewaktu memasuki viewport pengguna. Fitur ini dikontrol oleh `IntersectionObserver` berkinerja tinggi yang disematkan di dalam `MainLayout.astro`.
3. **Interactive Tabs & Smooth Scroll:**
   Sidebar navigasi pada halaman legalitas, syarat ketentuan, kebijakan privasi, dan kebijakan cookie secara otomatis menyoroti bagian yang sedang dibaca pengguna secara dinamis saat melakukan scroll (*Scroll Spy*), serta mendukung pergeseran posisi yang halus sewaktu tautan diklik.

---

## 📈 Rekomendasi Optimasi Masa Depan

1. **Komponen `<Image />` Astro:** Disarankan menggunakan modul `astro:assets` untuk melakukan kompresi otomatis gambar ke format modern seperti `.webp` atau `.avif` demi mempercepat pemuatan halaman.
2. **Integrasi Formulir Dinamis:** Form kontak di halaman `/contact` dan katalog produk dapat diintegrasikan dengan layanan pengolah formulir tanpa server (serverless form processors) seperti Formspree, Netlify Forms, atau Web3Forms.
3. **Penyimpanan Cache Global:** Memanfaatkan jaringan CDN seperti Cloudflare atau Vercel Edge Cache untuk memastikan waktu pemuatan halaman di bawah 1 detik bagi pembeli internasional di berbagai benua.
