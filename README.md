# Inventory App

Sistem manajemen inventaris modern dengan frontend di GitHub Pages dan backend di Google Apps Script.

## Struktur Project

```
inventory-app/
├── apps-script/          # Backend Google Apps Script
│   ├── Code.gs          # Kode utama Apps Script
│   └── Index.html       # Halaman Apps Script (opsional)
├── index.html           # Halaman utama aplikasi
├── package.json         # Konfigurasi npm (opsional)
├── .gitignore          # File yang diabaikan Git
└── README.md           # Dokumentasi ini
```

## Langkah Setup

### 1. Setup Google Apps Script (Backend)

1. Buka [Google Apps Script](https://script.google.com/)
2. Buat project baru
3. Salin konten dari `apps-script/Code.gs` ke editor
4. Buat Google Sheet baru untuk menyimpan data
5. Salin ID Spreadsheet Anda dan ganti `SPREADSHEET_ID` di `Code.gs`
6. Deploy project sebagai Web App:
   - Klik Deploy > New deployment
   - Pilih "Web app"
   - Set "Who has access" menjadi "Anyone"
   - Salin URL deployment (ini akan menjadi API endpoint Anda)

### 2. Setup Frontend (GitHub Pages)

1. Buka `index.html`
2. Cari URL Apps Script dan ganti dengan URL deployment Anda
3. Buat repository di GitHub
4. Upload seluruh folder `inventory-app/` ke GitHub

### 3. Aktifkan GitHub Pages

1. Di repository GitHub Anda, buka **Settings**
2. Gulir ke bagian **Pages**
3. Di bagian **Build and deployment**:
   - Source: Deploy from a branch
   - Branch: Pilih `main` / `master`
   - Folder: Pilih `/ (root)`
4. Klik **Save**
5. Tunggu beberapa menit, situs Anda akan tersedia di:
   `https://<username>.github.io/<repo-name>/`

### 4. Upload ke GitHub

```bash
cd inventory-app
git init
git add .
git commit -m "Initial commit"
git remote add origin <URL_REPOSITORY_GITHUB>
git push -u origin main
```

## Fitur Aplikasi

- Login dan autentikasi pengguna
- Manajemen data master inventaris
- Dashboard dengan statistik
- Generator barcode otomatis
- Approval workflow
- Multi-user dengan role-based access

## Teknologi

- **Frontend**: HTML, CSS, JavaScript (Vanilla)
- **Backend**: Google Apps Script
- **Database**: Google Sheets
- **Hosting**: GitHub Pages (frontend) & Google Apps Script (backend)

## Catatan Penting

- Pastikan CORS diaktifkan di Apps Script (sudah include di `Code.gs`)
- Jangan commit `SPREADSHEET_ID` asli ke repository publik
- Gunakan environment variables untuk konfigurasi sensitif
