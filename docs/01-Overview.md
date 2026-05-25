# Overview: Arisyafood Global Niaga

Selamat datang di repositori kode sumber *PT Arisyafood Global Niaga*. Proyek ini merupakan platform *Company Profile* berstandar B2B internasional, yang difokuskan pada penawaran produk agrikultur khas Nusantara (seperti rempah-rempah dan kerupuk ikan premium) untuk target ekspor.

## Teknologi Utama

Website ini dibangun menggunakan teknologi web modern yang berfokus pada kecepatan, SEO, dan kemudahan _maintenance_.

1. **Astro v6**: Web framework super cepat yang menghilangkan *JavaScript overhead* secara bawaan. Menghasilkan file HTML statis yang sempurna untuk kebutuhan *Search Engine Optimization* (SEO).
2. **Tailwind CSS v4**: Sistem *styling utility-first* untuk menciptakan desain yang konsisten, modern, dan sangat responsif di berbagai perangkat.
3. **HTML Statis Asli (*Native Sync*)**: Proyek ini memiliki alur khusus yang menyinkronkan hasil keluaran Astro kembali ke dalam format HTML tradisional, memungkinkan _hosting_ di ekosistem _legacy_ tanpa Node.js.

## Struktur Direktori

Untuk memudahkan navigasi bagi tim pengembang dan pengelola konten, berikut adalah peta struktur folder di dalam repositori ini:

```text
arisyafood/
├── src/                    # KODE SUMBER UTAMA (Area Kerja Developer)
│   ├── components/         # Kumpulan komponen modular (Atomic Design)
│   │   ├── atoms/          # Komponen terkecil (Button, Icon)
│   │   ├── molecules/      # Gabungan atoms (ProductCard, SEO, dll)
│   │   ├── organisms/      # Bagian besar halaman (Navbar, Footer, Carousel)
│   │   └── templates/      # Layout utama halaman (MainLayout)
│   ├── pages/              # Halaman Website (index, about, products, dll)
│   └── styles/             # Pengaturan CSS Global (global.css)
├── public/                 # ASSET STATIS (Area Kerja Desainer/Konten)
│   ├── images/             # Folder untuk menaruh semua foto/gambar produk
│   ├── fonts/              # File font khusus (Urbanist)
│   └── logo.png            # Logo utama perusahaan
├── native/                 # HASIL AKHIR STATIS (Area Produksi)
│   # Berisi salinan murni berformat .html yang siap dipublikasikan ke server tradisional.
├── dist/                   # Output sementara yang dihasilkan oleh perintah build Astro
└── docs/                   # Dokumentasi dan Manual Book (Anda berada di sini)
```

## Karakteristik Desain (UI/UX)

Desain website ini merujuk pada pedoman *Premium & Reliable*. Elemen visual kuncinya adalah:
- **Warna Utama**: Hijau Hutan (*Forest Green*) melambangkan kesegaran hasil bumi.
- **Warna Aksen**: Emas Panen (*Harvest Gold*) untuk menyoroti kualitas premium.
- **Tipografi**: Menggunakan **Urbanist** untuk tampilan korporat yang sangat bersih (*clean*).
- **Efek Modern**: Menyertakan animasi *Infinity Marquee* pada deretan logo sertifikasi, efek transisi kaca (*glassmorphism*), dan layar *loading* dengan *spinner* beraksen emas.

## Navigasi Dokumentasi

Silakan baca dokumen selanjutnya sesuai dengan peran Anda:
- **Untuk Admin/Pemilik Usaha**: Baca [02-User_Manual.md](./02-User_Manual.md) untuk panduan mengganti teks dan foto.
- **Untuk Developer Web**: Baca [03-Development_Guide.md](./03-Development_Guide.md) untuk pedoman kode dan optimasi SEO.
- **Untuk Tim IT/Hosting**: Baca [04-Deployment.md](./04-Deployment.md) untuk panduan sinkronisasi file ke server produksi.
