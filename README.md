# Kalkulator Beban Riba — jalanpulang.id
> Tools digital pendamping ebook **Terlanjur Riba** by Achmad Alief

---

## Struktur Project

```
riba-kalkulator/
├── index.html          ← Aplikasi utama (UI + scoring + PDF export)
├── api/
│   ├── analyze.js      ← Proxy Gemini API (analisis utama)
│   └── steps.js        ← Proxy Gemini API (langkah konkret)
├── vercel.json         ← Konfigurasi routing Vercel
└── README.md           ← Panduan ini
```

---

## Cara Deploy ke Vercel (Langkah Demi Langkah)

### Langkah 1 — Siapkan akun & tools

1. Buat akun **GitHub** di github.com (gratis)
2. Buat akun **Vercel** di vercel.com → klik "Sign Up with GitHub"
3. Install **Git** di komputermu: git-scm.com/downloads

### Langkah 2 — Dapatkan API Key Gemini (gratis)

1. Buka **aistudio.google.com**
2. Login dengan akun Google
3. Klik **"Get API Key"** → **"Create API key"**
4. Copy API key yang muncul (format: `AIzaSy...`)
5. **SIMPAN BAIK-BAIK** — jangan share ke siapapun

### Langkah 3 — Upload project ke GitHub

1. Buka **github.com** → klik tombol "+" → "New repository"
2. Nama repo: `riba-kalkulator` → klik "Create repository"
3. Di komputermu, buka terminal/command prompt di folder project ini
4. Jalankan perintah ini satu per satu:

```bash
git init
git add .
git commit -m "Initial commit — Kalkulator Beban Riba"
git branch -M main
git remote add origin https://github.com/NAMA_GITHUBMU/riba-kalkulator.git
git push -u origin main
```

*(Ganti `NAMA_GITHUBMU` dengan username GitHub-mu)*

### Langkah 4 — Deploy di Vercel

1. Buka **vercel.com** → klik "Add New Project"
2. Pilih repository `riba-kalkulator` → klik "Import"
3. Di bagian konfigurasi, **TIDAK PERLU diubah apapun** → langsung klik "Deploy"
4. Tunggu 1-2 menit → project berhasil di-deploy!
5. Kamu akan mendapat URL seperti: `riba-kalkulator.vercel.app`

### Langkah 5 — Set API Key (WAJIB)

1. Di Vercel dashboard → klik project-mu
2. Klik tab **"Settings"**
3. Di sidebar kiri, klik **"Environment Variables"**
4. Klik **"Add New"**:
   - **Name**: `GEMINI_API_KEY`
   - **Value**: paste API key Gemini-mu (AIzaSy...)
   - **Environments**: centang semua (Production, Preview, Development)
5. Klik **"Save"**
6. **PENTING**: Klik **"Redeploy"** agar env var aktif:
   - Ke tab "Deployments" → klik titik tiga di deployment terbaru → "Redeploy"

### Langkah 6 — Test

1. Buka URL Vercel-mu (contoh: `riba-kalkulator.vercel.app`)
2. Isi form lengkap → klik "Analisis"
3. Pastikan analisis AI muncul dan PDF bisa diunduh

---

## Custom Domain (Opsional)

Kalau ingin alamat `tools.jalanpulang.id`:

1. Di Vercel → Settings → Domains → Add domain
2. Masukkan: `tools.jalanpulang.id`
3. Vercel akan menampilkan DNS record yang harus ditambahkan
4. Buka panel hosting domain-mu (Niagahoster, Rumahweb, dll)
5. Tambahkan CNAME record sesuai petunjuk Vercel
6. Tunggu propagasi 5-60 menit → domain aktif!

---

## Update/Edit Konten

Setelah project di GitHub:
1. Edit file di komputermu
2. Jalankan: `git add . && git commit -m "Update" && git push`
3. Vercel otomatis redeploy dalam 1-2 menit ✓

---

## Batasan Free Tier

| Komponen | Gratis | Berbayar mulai |
|---|---|---|
| Vercel hosting | Selamanya | — |
| Gemini API | 1.500 req/hari | ~$0.075/1jt token |
| PDF generation | Selamanya (client-side) | — |
| Custom domain | Hanya domain-nya | ~Rp 150rb/thn |

Untuk 99% use case tools pendamping ebook, semua GRATIS.

---

## Troubleshooting Umum

**AI tidak muncul / error "AI service error"**
→ Cek apakah GEMINI_API_KEY sudah diset di Vercel → Settings → Environment Variables
→ Pastikan sudah Redeploy setelah set env var

**PDF tidak bisa diunduh**
→ Pastikan browser tidak memblokir popup/download
→ Coba di browser lain (Chrome direkomendasikan)

**Halaman tidak bisa diakses**
→ Cek vercel.json sudah ada di root project
→ Cek di Vercel dashboard → Functions tab untuk error log

---

## Keamanan

- ✅ API key Gemini **tidak pernah** terekspos ke browser user
- ✅ Data keuangan user **tidak disimpan** di server manapun
- ✅ PDF dibuat 100% di browser user (client-side)
- ✅ Tidak ada database, tidak ada logging data sensitif

---

## Kontak & Lisensi

**Dibuat oleh**: Achmad Alief  
**Ebook**: Terlanjur Riba — jalanpulang.id  
**Tools ini hak cipta penulis** — tidak boleh didistribusikan ulang tanpa izin

---

*Semoga tools ini menjadi jalan manfaat yang diridhai Allah. Aamiin.*
