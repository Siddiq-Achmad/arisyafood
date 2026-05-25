# Deployment & Native Synchronization

Dokumen ini menjelaskan alur kompilasi (*Build*) kode Astro menjadi paket rilis mandiri (HTML statis) dan bagaimana proses sinkronisasi (*Native Sync*) ke dalam folder tradisional.

## Filosofi "Static Site Generation" (SSG)

Berbeda dengan sistem *backend* monolitik (seperti WordPress atau Laravel) yang membutuhkan *rendering server-side* tiap kali diakses, Astro pada proyek ini dikonfigurasikan penuh sebagai mesin SSG. 

Seluruh komponen (`.astro`) dan Tailwind CSS akan diproses (*compiled*) pada saat **Build Time**, menghasilkan deretan kode murni `HTML`, `CSS`, dan `JavaScript` ringan yang bisa langsung diunggah (*upload*) ke layanan *hosting* statis termurah sekalipun (misal: cPanel tradisional, GitHub Pages, Vercel, Netlify).

---

## Proses Build

Untuk menghasilkan versi final dari kode Anda, jalankan perintah:

```bash
npm run build
```

**Apa yang terjadi saat proses ini berjalan?**
1. Astro memilah seluruh halaman di `src/pages/`.
2. Tailwind membersihkan kelas-kelas CSS yang tidak terpakai (*PurgeCSS*) dan menghasilkan satu *file* mini CSS akhir yang sangat ramping.
3. Seluruh *file* akan digabungkan dan diletakkan secara otomatis di dalam folder baru bernama `dist/`.
4. Sitemap (`sitemap-index.xml`) akan diproduksi.

Folder `dist/` inilah yang sebenarnya Anda perlukan untuk diletakkan ke *server hosting* utama Anda (dalam folder `public_html`).

---

## Sinkronisasi Folder Native (`native/`)

Klien/Pengguna memiliki preferensi arsitektur *legacy* (berisi file murni berakhiran `.html` tanpa perantara bundler JS). Untuk memfasilitasi hal ini sembari mempertahankan kecepatan *development* menggunakan komponen, proyek ini menerapkan kebijakan **Native Sync**.

Setelah Anda melakukan `npm run build`, isi direktori hasil (*output*) di folder `dist/` wajib digandakan ke folder `native/`.

### Alur Manual (Direkomendasikan):
Jika Anda mengubah konten halaman 404 dan 500, Anda bisa memindahkannya menggunakan *terminal command* UNIX:

```bash
cp dist/404.html native/404.html && cp dist/500.html native/500.html
```

*(Catatan: Untuk eksekusi ke depan, disarankan mengatur _script bash automation_ pada `package.json` untuk mengeksekusi penyalinan file ini secara otomatis pasca build)*.

> [!CAUTION]
> **JANGAN PERNAH** melakukan modifikasi manual secara langsung pada *file-file* di dalam folder `native/`. Folder ini hanyalah artefak cerminan dari `dist/`. Segala bentuk perubahan kode, *styling*, dan konten harus dilakukan melalui komponen Astro di folder `src/`. Jika Anda melanggarnya, perubahan tersebut akan tertimpa dan hilang saat proses kompilasi berikutnya.
