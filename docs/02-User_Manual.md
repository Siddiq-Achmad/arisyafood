# User Manual: Panduan Manajemen Konten

Dokumen ini adalah panduan praktis bagi Admin atau Pemilik Usaha untuk memperbarui konten website (teks, foto, produk) tanpa perlu memahami pemrograman secara mendalam.

---

## 1. Cara Mengganti Foto / Gambar

Semua gambar yang tampil di website diletakkan di dalam folder `public/images/`.

### Langkah-langkah:
1. Siapkan foto baru Anda. Pastikan nama filenya sederhana (misal: `krupuk-udang-baru.jpg`).
2. Masukkan (copy-paste) foto tersebut ke dalam folder `public/images/`.
3. Buka file halaman yang ingin Anda ubah fotonya (contoh: `src/pages/index.astro`).
4. Cari tulisan `src="/images/nama-foto-lama.jpg"`.
5. Ubah teks tersebut menjadi nama foto baru Anda: `src="/images/krupuk-udang-baru.jpg"`.

> [!TIP]
> **Ukuran Optimal:** Kompres gambar Anda terlebih dahulu menggunakan layanan gratis seperti *TinyPNG* agar website tetap memuat dengan cepat.

---

## 2. Cara Menambah / Menghapus Produk di Halaman Beranda (Carousel)

Produk unggulan yang tampil bergeser di halaman depan diatur di dalam file khusus.

### Langkah-langkah:
1. Buka file `src/components/organisms/ProductCarousel.astro`.
2. Pada baris awal (di bagian paling atas file), Anda akan melihat blok kode bernama `const carouselProducts = [...]`.
3. Di dalam kurung siku `[` dan `]`, terdapat susunan blok `{ ... }` untuk tiap produk.

**Untuk MENAMBAH produk baru,** ketik blok baru dengan format seperti ini:
```javascript
  {
    title: "Nama Produk Baru Anda",
    subtitle: "Keterangan singkat produk ini",
    image: "/images/foto-baru.jpg",
  },
```

**Untuk MENGHAPUS produk,** cukup hapus salah satu blok `{ ... },` dari daftar tersebut.

---

## 3. Cara Mengubah Teks Slogan / Profil Perusahaan

Konten teks untuk profil perusahaan tersebar di file halaman (`src/pages/`).

### Langkah-langkah:
1. Buka file halamannya, contoh `src/pages/about.astro` (Untuk halaman *About Us*).
2. Temukan paragraf Bahasa Inggris yang ingin Anda ubah. Biasanya teks tersebut diapit oleh tanda seperti `<p>` dan `</p>`.
   - Contoh kode: `<p class="text-body-lg">We are the leading exporter...</p>`
3. Ganti kalimat `We are the leading exporter...` menjadi kalimat baru Anda. **PENTING:** Jangan hapus tanda kurung `<p>` dan `<class="...">` di sekelilingnya.

---

## 4. Mengganti Nomor WhatsApp & Link Sosial Media

Informasi kontak dan sosial media muncul di dua tempat utama: Puncak halaman (Navbar) dan Bawah halaman (Footer).

### Mengubah Footer:
1. Buka `src/components/organisms/Footer.astro`.
2. Gunakan fitur pencarian (Ctrl+F atau Cmd+F) dan ketik `whatsapp` atau `linkedin`.
3. Anda akan menemukan kode `<a href="https://wa.me/6281234567890">`.
4. Ganti nomor atau *link* di dalam tanda kutip `href="..."` tersebut dengan nomor yang benar. Format WhatsApp internasional gunakan awalan `62` tanpa simbol plus (+).

### Mengubah Menu Atas (Navbar):
1. Buka `src/components/organisms/Navbar.astro`.
2. Lakukan pencarian nomor WhatsApp yang sama dan ubah sesuai panduan di atas.

---

## 5. Mengganti Logo Utama Perusahaan

Logo utama terletak persis di folder `public/`.
1. Nama file logo yang aktif adalah `logo.png`.
2. Jika Anda memiliki versi logo terbaru, pastikan file tersebut berbentuk PNG dengan latar transparan (tidak ada *background* putih).
3. Beri nama file baru tersebut `logo.png`.
4. Timpa (*overwrite*) file lama yang ada di dalam folder `public/` dengan file `logo.png` yang baru. Website akan secara otomatis menggunakan logo baru di semua halaman.
