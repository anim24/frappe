```markdown
# 📦 Frappe Bench Setup

Proyek ini adalah setup Frappe (dan/atau ERPNext) lengkap dengan konfigurasi `site`, custom app, dan panduan untuk menjalankannya secara lokal.

## 📁 Struktur Proyek

```bash
bench1/
├── app1/
│   └── app1/                 # Aplikasi kustom (opsional)
├── sites/
│   ├── site1/
│   │   └── site_config.json  # Konfigurasi database dan kunci enkripsi
│   └── apps.txt              # Daftar aplikasi yang terinstal
├── requirements.txt
├── Procfile
├── .gitignore
└── README.md
```

---

## 🚀 Cara Clone & Jalankan

### 1. Clone repo ini

```bash
git clone https://github.com/anim24/frappe.git
cd repo
```

### 2. Install Bench CLI (jika belum)

```bash
pip install frappe-bench
```

### 3. Setup environment

```bash
bench setup env
source env/bin/activate
pip install -r requirements.txt
```

### 4. Setup database site

Jika `site1` belum ada:

```bash
bench new-site site1
```

Jika kamu punya backup SQL:

```bash
bench --site site1 restore /path/to/database.sql
```

### 5. Jalankan server

```bash
bench start
```

Akses situs di: http://site1:8000

---

## 🧠 Catatan

- Pastikan `node`, `yarn`, `redis`, dan `mariadb` sudah terpasang di sistem.
- Untuk development di WSL, pastikan direktori `frappe-bench` ada di dalam filesystem Linux (`/home`), bukan `/mnt/c`.

---

## 🛠️ Troubleshooting

**❌ Error: `python3 -m venv env` failed**  
→ Jalankan `sudo apt install python3-venv`

**❌ Permission denied**  
→ Jalankan dengan `sudo` atau pastikan folder punya hak akses yang benar.

---

## 📜 Lisensi

MIT License.