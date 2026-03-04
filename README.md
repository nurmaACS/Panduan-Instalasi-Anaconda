# Panduan-Instalasi-Anaconda
Tugas Individu ML oleh Nurma (231001059)

# 🐍 Panduan Lengkap: Download, Install & Setup Anaconda

> **Versi Terbaru:** Anaconda Distribution 2025.12  
> **Python:** 3.13.9 | **Conda:** 25.11.0 | **Navigator:** 2.7.0

---

## 📋 Daftar Isi

1. [Persyaratan Sistem](#persyaratan-sistem)
2. [Download Anaconda](#download-anaconda)
3. [Instalasi di Windows](#instalasi-di-windows)
4. [Instalasi di macOS](#instalasi-di-macos)
5. [Instalasi di Linux](#instalasi-di-linux)
6. [Verifikasi Instalasi](#verifikasi-instalasi)
7. [Setup Awal & Konfigurasi](#setup-awal--konfigurasi)
8. [Perintah Conda Dasar](#perintah-conda-dasar)
9. [Membuat & Mengelola Environment](#membuat--mengelola-environment)
10. [Tips & Troubleshooting](#tips--troubleshooting)

---

## 💻 Persyaratan Sistem

| Platform | Minimum | Rekomendasi |
|----------|---------|-------------|
| **OS** | Windows 10/11, macOS 12.1+, Linux (glibc 2.28+) | Windows 11, macOS 13+, Ubuntu 22.04+ |
| **CPU** | 64-bit | 64-bit multi-core |
| **RAM** | 4 GB | 8 GB atau lebih |
| **Storage** | 5 GB | 10 GB+ |
| **Internet** | Diperlukan saat instalasi | - |

---

## ⬇️ Download Anaconda

### Cara 1: Via Website Resmi (Direkomendasikan)

1. Buka browser dan kunjungi: **[https://www.anaconda.com/download](https://www.anaconda.com/download)**
2. Pilih sistem operasi kamu (Windows / macOS / Linux)
3. Klik tombol **Download** untuk mengunduh installer

### Cara 2: Via Command Line (Linux/macOS)

```bash
# Cek versi terbaru di: https://repo.anaconda.com/archive/

# Linux (x86_64)
wget https://repo.anaconda.com/archive/Anaconda3-2025.12-Linux-x86_64.sh

# macOS (Apple Silicon / M1/M2/M3)
curl -O https://repo.anaconda.com/archive/Anaconda3-2025.12-MacOSX-arm64.sh

# macOS (Intel)
curl -O https://repo.anaconda.com/archive/Anaconda3-2025.12-MacOSX-x86_64.sh
```

> 📌 **Catatan:** Selalu unduh dari situs resmi Anaconda untuk keamanan.

---

## 🪟 Instalasi di Windows

### Langkah-langkah:

1. **Jalankan installer** — Double-click file `.exe` yang sudah didownload
2. **Welcome Screen** — Klik **Next**
3. **License Agreement** — Baca, lalu klik **I Agree**
4. **Installation Type** — Pilih salah satu:
   - `Just Me` ✅ *(Direkomendasikan untuk pengguna personal)*
   - `All Users` *(Butuh hak administrator)*
5. **Choose Install Location** — Biarkan default atau ubah sesuai kebutuhan:
   ```
   C:\Users\<NamaUser>\anaconda3
   ```
6. **Advanced Options** — Pengaturan penting:
   - ☑️ `Register Anaconda3 as my default Python` *(centang ini)*
   - ⬜ `Add Anaconda3 to my PATH` *(biarkan tidak dicentang, gunakan Anaconda Prompt)*
7. Klik **Install** dan tunggu hingga selesai (~5–10 menit)
8. Klik **Finish**

### Membuka Anaconda setelah instalasi:
- Cari **"Anaconda Prompt"** atau **"Anaconda Navigator"** di Start Menu

---

## 🍎 Instalasi di macOS

### Cara Grafis (GUI):

1. Buka file `.pkg` yang telah didownload
2. Ikuti wizard instalasi
3. Klik **Continue → Agree → Install**
4. Masukkan password admin jika diminta
5. Klik **Close** setelah selesai

### Cara Terminal:

```bash
# Masuk ke folder download
cd ~/Downloads

# Jalankan installer (sesuaikan nama file dengan yang didownload)
bash Anaconda3-2025.12-MacOSX-arm64.sh

# Ikuti instruksi di terminal:
# - Tekan ENTER untuk membaca lisensi
# - Ketik 'yes' untuk menyetujui lisensi
# - Tekan ENTER untuk konfirmasi lokasi instalasi
# - Ketik 'yes' untuk inisialisasi conda (conda init)
```

```bash
# Setelah instalasi, reload terminal
source ~/.zshrc   # Untuk macOS (Zsh - default)
# atau
source ~/.bashrc  # Jika menggunakan Bash
```

---

## 🐧 Instalasi di Linux

```bash
# Masuk ke direktori tempat file didownload
cd ~/Downloads

# Beri izin eksekusi pada file installer
chmod +x Anaconda3-2025.12-Linux-x86_64.sh

# Jalankan installer
bash Anaconda3-2025.12-Linux-x86_64.sh
```

### Ikuti prompt berikut:

| Prompt | Jawaban |
|--------|---------|
| Tekan ENTER untuk melihat lisensi | Tekan `ENTER` |
| Setuju dengan lisensi? | Ketik `yes` |
| Konfirmasi lokasi instalasi | Tekan `ENTER` (default: `~/anaconda3`) |
| Jalankan conda init? | Ketik `yes` |

```bash
# Aktifkan perubahan pada terminal
source ~/.bashrc

# Verifikasi instalasi
conda --version
```

---

## ✅ Verifikasi Instalasi

Buka **Anaconda Prompt** (Windows) atau **Terminal** (macOS/Linux):

```bash
# Cek versi conda
conda --version
# Output: conda 25.11.0

# Cek versi Python
python --version
# Output: Python 3.13.9

# Cek info lengkap
conda info

# Cek daftar paket yang terinstal
conda list
```

---

## ⚙️ Setup Awal & Konfigurasi

### 1. Update Conda ke Versi Terbaru

```bash
conda update -n base -c defaults conda
```

### 2. Update Semua Paket

```bash
conda update --all
```

### 3. Tambahkan Channel conda-forge (Opsional tapi direkomendasikan)

```bash
# Tambah channel conda-forge
conda config --add channels conda-forge

# Set prioritas channel
conda config --set channel_priority strict
```

### 4. Konfigurasi Conda (opsional)

```bash
# Nonaktifkan aktivasi otomatis environment base
conda config --set auto_activate_base false

# Tampilkan nama environment di prompt
conda config --set changeps1 true
```

### 5. Buka Anaconda Navigator (GUI)

```bash
anaconda-navigator
```

---

## 📦 Perintah Conda Dasar

```bash
# Mencari paket
conda search numpy

# Install paket
conda install numpy

# Install paket dengan versi tertentu
conda install numpy=1.26.0

# Update paket tertentu
conda update numpy

# Hapus paket
conda remove numpy

# Lihat daftar paket di environment aktif
conda list

# Update semua paket
conda update --all
```

---

## 🌐 Membuat & Mengelola Environment

### Membuat Environment Baru

```bash
# Buat environment dengan Python versi tertentu
conda create -n myenv python=3.11

# Buat environment beserta paket
conda create -n datascience python=3.11 numpy pandas matplotlib scikit-learn
```

### Mengaktifkan & Menonaktifkan Environment

```bash
# Aktifkan environment
conda activate myenv

# Kembali ke base
conda deactivate
```

### Mengelola Environment

```bash
# Lihat semua environment
conda env list
# atau
conda info --envs

# Hapus environment
conda env remove -n myenv

# Export environment ke file
conda env export > environment.yml

# Buat environment dari file
conda env create -f environment.yml

# Clone environment
conda create --name myenv_copy --clone myenv
```

### Contoh Workflow Lengkap

```bash
# 1. Buat environment baru
conda create -n proyek_ml python=3.11

# 2. Aktifkan
conda activate proyek_ml

# 3. Install paket yang dibutuhkan
conda install numpy pandas matplotlib scikit-learn jupyter

# 4. Jalankan Jupyter Notebook
jupyter notebook

# 5. Setelah selesai, nonaktifkan
conda deactivate
```

---

## 🔧 Tips & Troubleshooting

### ❓ conda tidak dikenali setelah instalasi (Windows)

Gunakan **Anaconda Prompt** bukan Command Prompt biasa. Atau tambahkan Anaconda ke PATH:
```
C:\Users\<NamaUser>\anaconda3
C:\Users\<NamaUser>\anaconda3\Scripts
C:\Users\<NamaUser>\anaconda3\Library\bin
```

### ❓ conda tidak dikenali di Terminal (macOS/Linux)

```bash
# Jalankan conda init ulang
~/anaconda3/bin/conda init bash   # Jika menggunakan bash
~/anaconda3/bin/conda init zsh    # Jika menggunakan zsh

# Restart terminal atau jalankan:
source ~/.bashrc  # atau ~/.zshrc
```

### ❓ Instalasi paket gagal / konflik dependensi

```bash
# Gunakan conda-forge sebagai solusi alternatif
conda install -c conda-forge nama_paket

# Atau gunakan pip (sebagai alternatif terakhir)
pip install nama_paket
```

### ❓ Environment tidak muncul di Jupyter Notebook

```bash
# Aktifkan environment dulu
conda activate myenv

# Install ipykernel
conda install ipykernel

# Daftarkan sebagai kernel
python -m ipykernel install --user --name myenv --display-name "Python (myenv)"

# Buka Jupyter
jupyter notebook
```

### ❓ Anaconda berjalan lambat

```bash
# Bersihkan cache conda
conda clean --all

# Gunakan mamba sebagai pengganti conda (lebih cepat)
conda install -c conda-forge mamba
mamba install numpy  # Lebih cepat dari conda install
```

---

## 📚 Referensi & Sumber Belajar

| Sumber | Link |
|--------|------|
| 🌐 Website Resmi | [anaconda.com](https://www.anaconda.com) |
| 📖 Dokumentasi Conda | [docs.conda.io](https://docs.conda.io) |
| 📦 Anaconda Package Repository | [anaconda.org](https://anaconda.org) |
| 💬 Forum Komunitas | [community.anaconda.com](https://community.anaconda.com) |
| 🐛 Release Notes 2025.12 | [anaconda.com/docs](https://www.anaconda.com/docs/getting-started/anaconda/release/2025.x) |

---

> 💡 **Tips:** Selalu gunakan **environment terpisah** untuk setiap proyek agar tidak terjadi konflik antar paket!

*Panduan ini dibuat berdasarkan Anaconda Distribution 2025.12 (Desember 2025)*
