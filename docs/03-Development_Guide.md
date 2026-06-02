# Development Guide

Dokumen ini ditujukan bagi *Web Developer* yang ingin mengembangkan struktur, menambahkan fitur, atau memperbaiki masalah teknis (*bugs*) pada website ini.

## Menjalankan Server Lokal (Development)

Website ini menggunakan Node.js dan **Astro**. Pastikan Anda telah menginstal `Node.js >= 22.12.0`.

1. Buka Terminal / *Command Prompt*.
2. Arahkan *path* ke *root directory* proyek ini (`cd arisyafood`).
3. Jalankan perintah instalasi dependensi (hanya saat pertama kali):
   ```bash
   npm install
   ```
4. Jalankan *development server*:
   ```bash
   npm run dev
   ```
5. Akses website lokal pada URL: `http://localhost:4321`.

Sistem *Hot-Reload* sudah tertanam. Setiap perubahan yang Anda simpan (`Ctrl+S`) pada file `.astro`, `.css`, atau `.html` akan langsung direfleksikan di *browser* tanpa perlu memuat ulang (*refresh*) secara manual.

---

## Arsitektur Modular (Atomic Design)

Astro diformat untuk sangat kompartemental. Modifikasi harus dilakukan dengan menjaga prinsip hirarki:
*   **Atoms (`src/components/atoms/`)**: Elemen dasar yang tidak bisa dipecah lagi. Contoh: `Button.astro`, `Icon.astro`.
*   **Molecules (`src/components/molecules/`)**: Kumpulan atom. Contoh: `ProductCard.astro` (berisi elemen teks dan gambar).
*   **Organisms (`src/components/organisms/`)**: Susunan kompleks penopang antarmuka. Contoh: `ProductCarousel.astro`, `Navbar.astro`.
*   **Templates (`src/components/templates/`)**: Wadah (*wrapper*) layout halaman. Contoh: `MainLayout.astro` di mana *Header*, *Footer*, dan *Global Loader* ditanamkan secara global.

## Penanganan Error Global (404 & 500)

Sistem telah memiliki penanganan *error* tingkat *server* dan *client*:
- **404 Not Found**: Dikelola oleh `src/pages/404.astro`.
- **500 Server Error**: Dikelola oleh `src/pages/500.astro`.
- Keduanya didesain khusus agar menyatu dengan *MainLayout* sehingga pengguna tidak dihadapkan dengan pesan bawaan peramban (*browser default*).

## Sistem Layar Muat (Global Loader)

Untuk menghadirkan pengalaman pengguna ala aplikasi modern bergaya *enterprise*, kami menanamkan `GlobalLoader.astro` tepat di bawah tag `<body>` pada `MainLayout.astro`.

**Cara Kerja:**
- Menggunakan CSS penuh layar (`fixed inset-0 z-[9999]`) menutupi konten utama.
- Mendengarkan perintah *Event Listener* `window.onload`. Begitu *browser* memberikan sinyal bahwa seluruh DOM dan gambar selesai dirender, script akan memicu efek *fade-out* (transisi CSS `opacity: 0` berdurasi lambat).
- Memiliki sistem detak waktu darurat (*fallback timer*) selama 5 detik untuk berjaga-jaga jika skrip `window.onload` gagal ditembakkan akibat perangkat atau ekstensi pemblokir (*ad-blocker*).

## Struktur SEO dan JSON-LD (Schema Markup)

Platform ini mengimplementasikan AEO/SEO teknis kelas tinggi.
1. Setiap halaman di dalam `src/pages/` **WAJIB** menyisipkan atribut `title` dan `description` melalui props ke `<MainLayout>`.
2. Komponen `src/components/molecules/SEO.astro` secara otomatis meng- *generate* metatag `OpenGraph` (untuk *preview* WhatsApp/LinkedIn) dan `Twitter Cards`.
3. Komponen ini dirancang untuk menerima properti `schemaData` berupa array objek JSON. Anda dapat menyuntikkan berbagai skema dinamis (seperti `WebSite`, `FAQPage`, `AboutPage`, `ItemList`, dan `ContactPage`) langsung dari halaman masing-masing untuk memudahkan mesin pencari (Google) dan mesin penjawab AI (Answer Engine) mengidentifikasi struktur data *PT Arisyafood Global Niaga*.

## Aksesibilitas (A11y / WCAG)

Dalam pengembangan atau penambahan fitur, pastikan antarmuka memenuhi standar aksesibilitas:
- **ARIA Roles**: Gunakan peran ARIA yang tepat (seperti `role="tablist"`, `role="tab"`, dan `role="tabpanel"`) pada elemen interaktif seperti kategori produk.
- **Form Labels**: Pastikan setiap tag `<label>` terhubung secara eksplisit ke elemen input (menggunakan atribut `for` dan `id`). Untuk *checkbox* atau *radio button*, kelompokkan menggunakan `<fieldset>` dan `<legend>`.
- **Atribut Gambar**: Setiap elemen `<img/>` harus memiliki atribut `alt` yang deskriptif untuk *screen reader*. Gambar pahlawan (*Hero*) harus dilengkapi dengan `fetchpriority="high"`.

> [!WARNING]
> Jika Anda menambah halaman navigasi baru (misal: `/cabang-baru`), pastikan untuk menjalakan `npm run build` setelahnya agar sitemap (`sitemap-index.xml`) otomatis diperbarui oleh integrasi `@astrojs/sitemap`.
