# S-GATE — Prototipe Fase 1

Aplikasi ini adalah prototipe statis (single HTML file) yang bisa langsung dibuka di browser
tanpa server/backend. File `index.html` sudah berisi semua CSS & JS di dalamnya, jadi cukup
di-hosting sebagai situs statis.

File `sgate-database.xlsx` disertakan sebagai referensi struktur data (sheet EMKL, DO,
Kontainer, Log Notifikasi) — bukan file yang di-load otomatis oleh aplikasi, karena aplikasi
menyimpan datanya sendiri di memori browser saat berjalan.

---

## 1. Upload ke GitHub

Buka Terminal / Command Prompt, masuk ke folder ini, lalu jalankan:

```bash
git init
git add .
git commit -m "Initial commit: S-GATE prototype"
```

Buat repository baru di GitHub (lewat web: https://github.com/new), lalu hubungkan:

```bash
git branch -M main
git remote add origin https://github.com/USERNAME/NAMA-REPO.git
git push -u origin main
```

Ganti `USERNAME` dan `NAMA-REPO` sesuai akun dan nama repo yang kamu buat.

> Tidak punya Git terinstal? Alternatif tanpa terminal: buka repo baru di GitHub → tombol
> **"uploading an existing file"** → drag & drop semua file di folder ini → commit langsung
> dari browser.

---

## 2. Deploy ke Netlify

Ada dua cara paling mudah:

### Cara A — Drag & drop (paling cepat, tanpa GitHub)
1. Buka https://app.netlify.com/drop
2. Drag folder ini (atau file `index.html`-nya) ke halaman tersebut.
3. Netlify langsung memberi URL live (mis. `https://nama-acak.netlify.app`).

### Cara B — Lewat GitHub (otomatis update tiap kali push)
1. Push dulu folder ini ke GitHub (lihat langkah 1 di atas).
2. Login ke https://app.netlify.com → **Add new site** → **Import an existing project**.
3. Pilih GitHub, lalu pilih repo yang baru dibuat.
4. Build settings dibiarkan default (tidak perlu build command, karena ini situs statis):
   - Build command: *(kosongkan)*
   - Publish directory: `.`
5. Klik **Deploy site**.

File `netlify.toml` di folder ini sudah menyiapkan konfigurasi dasar (publish directory `.`
dan sedikit header keamanan), jadi Netlify akan otomatis mendeteksinya.

---

## Isi folder
- `index.html` — aplikasi S-GATE (dari `sgate-prototype.html`)
- `sgate-database.xlsx` — referensi struktur data
- `netlify.toml` — konfigurasi deploy Netlify
- `.gitignore` — file/folder yang diabaikan Git
