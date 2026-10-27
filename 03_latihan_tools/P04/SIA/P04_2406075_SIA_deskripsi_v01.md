# Tabel Deskripsi Use Case

## SIA-UC08 — Input Nilai Mata Kuliah
| Elemen | SIA-UC08 — Input Nilai Mata Kuliah |
|---|---|
| Sumber kebutuhan | SIA-R08 |
| Tujuan | Dosen dapat memasukkan nilai mahasiswa pada mata kuliah yang diampunya. |
| Aktor utama | Dosen |
| Aktor pendukung | Tidak ada |
| Pemicu | Dosen memilih menu input nilai mata kuliah. |
| Prasyarat | Dosen sudah login dan merupakan pengampu mata kuliah yang dipilih. |
| Alur utama | 1. Dosen membuka menu input nilai.<br>2. Sistem menampilkan mata kuliah yang diampu dosen.<br>3. Dosen memilih mata kuliah dan mahasiswa.<br>4. Dosen memasukkan nilai.<br>5. Sistem memeriksa rentang nilai.<br>6. Sistem menyimpan nilai dan menampilkan konfirmasi. |
| Alur alternatif/pengecualian | Jika nilai berada di luar rentang yang sah, sistem menolak nilai dan menampilkan pesan kesalahan. Dosen harus memasukkan nilai yang valid. |
| Pascakondisi berhasil | Nilai berhasil disimpan, tetapi belum ditampilkan pada KHS sebelum dipublikasikan. |
| Pascakondisi gagal | Nilai tidak tersimpan apabila validasi gagal atau proses penyimpanan mengalami kegagalan. |
| Aturan bisnis/asumsi | Hanya dosen pengampu yang boleh memasukkan nilai. KHS hanya menampilkan nilai yang sudah dipublikasikan. |
| Collaboration | SIA-CO01 — Input Nilai Mata Kuliah |

## SIA-UC09 — Lihat KHS

| Elemen | SIA-UC09 — Lihat KHS |
|---|---|
| Sumber kebutuhan | SIA-R09 |
| Tujuan | Mahasiswa dapat melihat Kartu Hasil Studi (KHS). |
| Aktor utama | Mahasiswa |
| Deskripsi ringkas | Mahasiswa memilih menu KHS dan semester yang ingin dilihat. Sistem hanya menampilkan nilai yang sudah dipublikasikan. |
| Collaboration | SIA-CO02 — Lihat KHS |