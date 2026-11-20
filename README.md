# KESC & KEYSI 2027 — Official Website

Repository resmi untuk website informasi dan pendaftaran **King Expert Science Competition (KESC) 2027** serta **King Expert Young Science Ideation (KEYSI) 2027** yang diselenggarakan oleh **King Expert**.

- **Website Produksi (Live):** [https://www.kesc-heei.com](https://www.kesc-heei.com)
- **Domain Cadangan Vercel:** [https://kesc-web.vercel.app](https://kesc-web.vercel.app)
- **Repository GitHub:** [https://github.com/kingexpert-id/kesc-web](https://github.com/kingexpert-id/kesc-web)

---

## Tech Stack & Arsitektur

Website ini dibangun dengan pendekatan **Static Site Generation (SSG)** untuk kecepatan akses maksimal dan stabilitas tinggi tanpa ketergantungan *server-side runtime*:

- **Framework:** [Astro v7](https://astro.build/)
- **Styling:** Tailwind CSS v4 dengan kustomisasi *Design System Tokens*
- **Bahasa:** TypeScript, HTML, CSS
- **Hosting & CI/CD:** Vercel (terintegrasi otomatis dengan repository GitHub ini)

---

## Struktur Halaman (Routes)

Setiap file `.astro` di dalam direktori `src/pages/` otomatis diekspos sebagai rute halaman berdasarkan nama filenya:

| Rute | Halaman | Deskripsi |
| :--- | :--- | :--- |
| `/` | **Beranda** | Ringkasan acara KESC & KEYSI 2027, keunggulan kompetisi, dan CTA pendaftaran utama. |
| `/kesc` | **Program KESC 2027** | Detail kompetisi sains berbasis CBT (SD/MI, SMP/MTs, SMA/SMK/MA), daftar mata pelajaran, harga, dan panduan. |
| `/keysi` | **Program KEYSI 2027** | Detail kompetisi esai & gagasan ilmiah (SMP/MTs, SMA/SMK/MA, Mahasiswa), topik karya, ketentuan video, dan panduan. |
| `/jadwal` | **Jadwal Kompetisi** | Linimasa pendaftaran *Early Bird*, *Regular*, pelaksanaan lomba, hingga penetapan juara. |
| `/pengumuman` | **Pengumuman & Arsip** | Akses soal & pembahasan edisi sebelumnya serta dokumen SK Finalis dan Pemenang. |
| `/faq` | **FAQ** | Jawaban atas pertanyaan umum seputar mekanisme peserta, biaya pendaftaran, dan teknis pelaksanaan. |

---

## Project Structure

```text
kesc-web/
├── .vscode/             # Konfigurasi rekomendasi editor & ekstensi workspace
├── public/              # Aset statis yang disajikan langsung tanpa proses bundling
│   ├── images/          # Aset gambar, poster resmi, dan ilustrasi halaman
│   ├── favicon.ico
│   └── favicon.svg
├── src/                 # Kode sumber utama aplikasi Astro
│   ├── components/      # Komponen UI reusable (kartu harga, navigasi, footer, dll.)
│   ├── layouts/         # Template layout dasar halaman
│   └── pages/           # Routing halaman berbasis file (.astro)
├── AGENTS.md            # Panduan aturan kerja untuk AI Coding Agent
├── astro.config.mjs     # Konfigurasi utama Astro & integrasi Tailwind CSS v4
├── package.json         # Daftar dependensi dan skrip NPM
├── package-lock.json    # Pengunci versi dependensi proyek
└── tsconfig.json        # Konfigurasi TypeScript
```

---

## Getting Started (Pengembangan Lokal)

Pastikan **Node.js** sudah terpasang di perangkat Anda sebelum memulai pengembangan lokal.

1. **Clone repository dan masuk ke direktori proyek:**
   ```bash
   git clone [https://github.com/kingexpert-id/kesc-web.git](https://github.com/kingexpert-id/kesc-web.git)
   cd kesc-web
   ```

2. **Instal seluruh dependensi proyek:**
   ```bash
   npm install
   ```

3. **Jalankan server pengembangan lokal:**
   ```bash
   npm run dev
   ```
   Buka `http://localhost:4321` di browser untuk memantau perubahan tampilan secara langsung (*hot-reload*).

---

## Commands (NPM & Astro CLI)

Seluruh perintah berikut dijalankan dari direktori root proyek (`kesc-web/`):

| Command | Action |
| :--- | :--- |
| `npm install` | Menginstal seluruh dependensi yang tercatat di `package.json`. |
| `npm run dev` | Menjalankan server pengembangan lokal di `localhost:4321`. |
| `npm run build` | Mengompilasi situs produksi statis ke direktori `./dist/`. |
| `npm run preview` | Menjalankan pratinjau hasil *build* produksi secara lokal sebelum di-deploy. |
| `npm run astro ...` | Menjalankan perintah CLI Astro seperti `astro add` atau `astro check`. |
| `npm run astro -- --help` | Menampilkan daftar lengkap bantuan perintah Astro CLI. |
| `npx @astrojs/upgrade` | Memperbarui versi Astro dan integrasi resminya ke versi terbaru. |

---

## Alur Kerja Git & Deployment (Branching Strategy)

Repository ini menggunakan dua *branch* utama untuk menjaga kestabilan situs produksi:

- **`main` (Production):** Branch utama yang terhubung langsung ke domain produksi **`www.kesc-heei.com`**. Hindari melakukan *push* langsung ke branch ini sebelum perubahan diuji.
- **`preview` (Staging / QA):** Branch kerja untuk mengedit konten, memperbarui komponen UI, dan menguji fitur baru. Setiap *push* ke branch `preview` otomatis memperbarui *Preview URL* di Vercel untuk ditinjau tim sebelum digabungkan (*merge*) ke `main`.

### Urutan Update Kode:
1. Pastikan posisi Git aktif berada di branch **`preview`**.
2. Lakukan perubahan kode dan uji melalui `npm run dev` serta `npm run build`.
3. *Commit* dan *push* perubahan ke branch **`preview`**, lalu verifikasi tampilan di *Preview URL* Vercel.
4. Jika seluruh revisi sudah disetujui, buat *Pull Request* dan *merge* dari **`preview`** ke **`main`**.

---

## Dokumentasi & Referensi Astro

- **Panduan Memulai Astro:** [Astro Getting Started](https://docs.astro.build/en/getting-started/)
- **Dokumentasi Resmi Astro:** [Astro Documentation](https://docs.astro.build)
- **Komunitas Pengembang:** [Astro Official Discord](https://astro.build/chat)

---

## Pengelola Proyek

- **Penyelenggara:** King Expert (`@kingexpert-id`)