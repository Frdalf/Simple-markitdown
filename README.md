# Simple MarkItDown Web

Sebuah aplikasi web statis sederhana untuk mengonversi berbagai format dokumen (PDF, Word, Excel, PowerPoint, HTML, dll) menjadi file Markdown (`.md`).

Aplikasi ini menggunakan [Pyodide](https://pyodide.org/) untuk menjalankan [MarkItDown](https://github.com/microsoft/markitdown) secara lokal langsung di dalam browser pengguna (client-side), sehingga menjamin privasi karena file tidak pernah diunggah ke server manapun.

## Fitur
- **Drag & Drop:** Antarmuka mudah digunakan.
- **Client-Side Processing:** Konversi dilakukan langsung di browser Anda menggunakan WebAssembly.
- **Format yang Didukung:** PDF, DOCX, PPTX, XLSX, XLS, HTML, CSV, JSON, XML, TXT, EPUB, dan ZIP.

## Cara Penggunaan
1. Buka file `index.html` di browser Anda atau kunjungi halaman yang sudah di-deploy.
2. Klik kotak area atau seret file dokumen yang ingin dikonversi ke dalam kotak tersebut.
3. Tunggu proses konversi selesai.
4. File `.md` akan otomatis terunduh ke komputer Anda.

## Deployment (Hosting)
Karena ini adalah file HTML statis murni tanpa kebutuhan server backend, aplikasi ini sangat ideal untuk di-host menggunakan layanan statis gratis seperti:
- [Cloudflare Pages](https://pages.cloudflare.com/) (Direkomendasikan)
- [GitHub Pages](https://pages.github.com/)
- [Vercel](https://vercel.com/)
- [Netlify](https://www.netlify.com/)

Cukup hubungkan repository GitHub Anda ke layanan di atas, atau unggah langsung file `index.html` ini.
