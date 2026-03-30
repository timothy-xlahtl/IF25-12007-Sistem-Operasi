# IF25-12007 Sistem Operasi - Repositori Dokumen Praktikum Berbasis LaTeX

Repositori ini menyediakan template dan materi dokumen akademik untuk mata kuliah **Sistem Operasi (IF25-12007)** di Institut Teknologi Sumatera (ITERA), meliputi:
- **Modul Praktikum** (dokumen instruksi praktikum per pertemuan)
- **Hands-On** (tugas mahasiswa)
- **Template Laporan** (template generik laporan hands-on)

---

## Daftar Modul

| No. | Topik | File |
|-----|-------|------|
| 1  | Pengenalan Antarmuka OS dan Virtual Machine | `chapters/modul_01.tex` |
| 2  | Instalasi Ubuntu pada VirtualBox | `chapters/modul_02.tex` |
| 3  | Navigasi dan Manajemen Izin File Linux | `chapters/modul_03.tex` |
| 4  | Automasi dengan Bash Scripting | `chapters/modul_04.tex` |
| 5  | Sistem Build dengan GCC | `chapters/modul_05.tex` |
| 6  | Otomatisasi Proses Build dengan Makefile | `chapters/modul_06.tex` |
| 7  | Booting dan Framework Sistem Operasi | `chapters/modul_07.tex` |
| 8  | Implementasi Multi-threading | `chapters/modul_08.tex` |
| 9  | Analisis Race Condition | `chapters/modul_09.tex` |
| 10 | Implementasi Mutex dan Locks | `chapters/modul_10.tex` |
| 11 | Penjadwalan Proses Round-Robin | `chapters/modul_11.tex` |
| 12 | Penjadwalan Proses Berbasis Prioritas | `chapters/modul_12.tex` |

---

## 1. Overview

### Tujuan

- Menyediakan standar penulisan dokumen praktikum berbasis LaTeX.
- Memudahkan dosen, asisten, dan mahasiswa dalam menyusun modul dan laporan.
- Menjaga konsistensi format akademik antar dokumen praktikum.

### Ruang Lingkup

- Penyusunan modul praktikum per topik.
- Penyusunan dokumen hands-on mahasiswa.
- Pengelolaan referensi ilmiah menggunakan BibTeX.
- Dokumentasi bukti eksperimen (gambar/screenshot) secara sistematis.

### Target Pengguna

- **Asisten Praktikum**: pengelolaan materi, hands-on, dan evaluasi hands-on.
- **Mahasiswa**: penyusunan laporan praktikum sesuai template.

---

## 2. Repository Structure

```text
IF25-12007-Sistem-Operasi/
├── README.md
├── Modul Praktikum/
│   ├── main.tex
│   ├── config.sty
│   ├── Referensi.bib
│   ├── chapters/
│   │   ├── modul_01.tex
│   │   ├── ...
│   │   └── modul_12.tex
│   ├── Figure/
│   │   ├── 00/ 01/ ... 12/
│   │   └── ifitera-header.png
│   └── %OUTDIR%/
├── Hands-On/
│   ├── main.tex
│   ├── config.sty
│   ├── Referensi.bib
│   ├── chapters/
│   │   ├── handson_01.tex
│   │   ├── ...
│   │   └── handson_06.tex
│   ├── Figure/
│   │   ├── 1/ 2/ ... 6/
│   │   └── ifitera-header.png
│   └── %OUTDIR%/
└── Template Laporan/
    ├── main.tex
    ├── config.sty
    ├── Referensi.bib
    ├── chapters/
    │   └── template.tex
    ├── Figure/
    │   └── ifitera-header.png
    └── %OUTDIR%/
```

---

## 3. Document Structure

### A. Modul Praktikum

Setiap file `modul_XX.tex` mengikuti alur akademik:
1. Tujuan dan Output Praktikum
2. Dasar Teori
3. Alat dan Bahan
4. Langkah-Langkah Praktikum

Alur ini mendukung pembelajaran berbasis outcome dari teori ke praktik.

### B. Hands-On

Setiap `handson_XX.tex` dirancang untuk tugas mandiri praktikan.

### C. Template Laporan

`Template Laporan/chapters/template.tex` memuat struktur laporan akademik lengkap:
- Pendahuluan
- Dasar Teori
- Alat dan Bahan
- Langkah-Langkah
- Pembahasan
- Kesimpulan
- Lampiran penggunaan AI

---

## 4. How to Compile

### Prasyarat

Gunakan salah satu distribusi LaTeX:
- TeX Live
- MiKTeX
- MacTeX

Atau editor online seperti Overleaf atau Prism.

### Opsi 1 - `latexmk` (disarankan)

```bash
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

### Opsi 2 - `pdflatex` + `bibtex`

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

### Kompilasi per dokumen

Jalankan per folder:
- `Modul Praktikum/main.tex`
- `Hands-On/main.tex`
- `Template Laporan/main.tex`

### Overleaf

1. Unggah seluruh isi folder target (misalnya `Modul Praktikum/`).
2. Set `Main document` ke `main.tex`.
3. Klik **Compile**.

---

## 6. Writing Guidelines

### Menambah modul/chapter baru

- Buat file baru di `chapters/` dengan pola nama `modul_XX.tex` atau `handson_XX.tex`.
- Tambahkan `\input{chapters/nama_file}` di `main.tex`.

### Menambah referensi

- Tambahkan entri BibTeX di `Referensi.bib`.
- Sitasi di teks dengan `\cite{key}`.
- Gunakan gaya sitasi yang sudah ditetapkan (`IEEEtran`).

### Menambah gambar

- Simpan gambar pada folder `Figure/XX/` sesuai modul.
- Gunakan format berikut:

```latex
\begin{figure}[H]
  \centering
  \includegraphics[width=0.75\textwidth]{Figure/XX/nama-gambar.png}
  \caption{Caption informatif dan ringkas}
  \label{fig:mXX-nama-gambar}
\end{figure}
```

### Menambah tabel

- Gunakan caption yang menjelaskan isi tabel.
- Letakkan `\label` setelah `\caption`.
- Gunakan prefix label yang konsisten (`tab:`).

---

## 7. Key Notes / Conventions

### Konvensi penamaan file

- Modul: `modul_01.tex`, `modul_02.tex`, dan seterusnya.
- Hands-on: `handson_01.tex`, `handson_02.tex`, dan seterusnya.
- Gambar: gunakan nama deskriptif, misalnya `setup-virtualbox.png`, bukan `gambar1.png`.

### Konvensi label

Disarankan:
- Chapter: `chap:modul-xx`
- Section: `sec:mxx-topik`
- Figure: `fig:mxx-topik`
- Table: `tab:mxx-topik`
- Listing: `kode:mxx-topik`

---

## Lisensi

Template ini dibuat untuk dipergunakan oleh Sivitas Akademik ITERA, khususnya Program Studi Teknik Informatika ITERA.
