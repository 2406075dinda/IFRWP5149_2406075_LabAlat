# Deskripsi skenario
Sistem Informasi Akademik, Layanan Hasil Studi 
Tugas ini berbeda dari tugas pertemuan sebelumnya. Tugas Pertemuan 2 
adalah jadwal kuliah dan tugas Pertemuan 3 adalah pengajuan KRS. Tugas 
Pertemuan 4 adalah layanan hasil studi, dengan teknik generalization dan 
collaboration yang sama seperti studi kasus, tetapi diterapkan pada skenario 
baru tanpa contoh jawaban. 
Skenario tugas berikut fiktif untuk praktikum dan berbeda dari tugas 
Pertemuan 2 (jadwal kuliah) dan Pertemuan 3 (pengajuan KRS). 
Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang 
dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang 
diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu 
Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin 
Akademik mengelola data mahasiswa: menambah data mahasiswa baru, 
mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case 
utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh 
collaboration yang bersesuaian.

# Batas dan asumsi 
• Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01 dan SIA-R02 
(Pertemuan 2) serta SIA-R03 sampai SIA-R06 (Pertemuan 3) tetap 
mempunyai identitas berbeda. 
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. 
• Kalender akademik pada tugas ini adalah agenda resmi institusi (awal 
semester, batas KRS, masa ujian, dan sejenisnya); jangan 
menyamakannya dengan jadwal kuliah pada Pertemuan 2. 
• Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai 
yang diinput belum terpublikasi sebelum dinyatakan resmi oleh ketentuan 
tugas ini: KHS hanya menampilkan nilai yang sudah dipublikasikan. 
• Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data 
akademik aktif. Ketentuan ini fiktif untuk latihan. 
• Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari 
Pertemuan 3. Pembayaran dan perancangan basis data berada di luar 
tugas ini.

# identifikasi aktor
| Aktor | Kedudukan | Tujuan terhadap Sistem |
|---|---|---|
| Civitas Akademika | Aktor umum | Melihat kalender akademik. |
| Mahasiswa | Aktor khusus dari Civitas Akademika | Melihat jadwal kuliah, mengajukan KRS, mengunduh bukti pengajuan KRS, dan melihat KHS. |
| Dosen | Aktor khusus dari Civitas Akademika | Melihat kalender akademik dan menginput nilai mata kuliah yang diampunya. |
| Admin Akademik | Aktor mandiri | Mengelola jadwal kuliah serta menambah, mengubah, dan menghapus data mahasiswa. |
| Dosen Wali | Aktor mandiri | Memproses keputusan KRS mahasiswa. |

# Katalog Use Case
| ID | Nama Use Case | Aktor Terkait | Sumber Kebutuhan | Status |
|---|---|---|---|---|
| SIA-UC01 | Lihat Jadwal Kuliah | Mahasiswa | SIA-R01 | Tetap |
| SIA-UC02 | Kelola Jadwal Kuliah | Admin Akademik | SIA-R02 | Tetap |
| SIA-UC03 | Ajukan KRS | Mahasiswa | SIA-R03 | Tetap |
| SIA-UC04 | Validasi KRS | Sistem | SIA-R04 | Tetap |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa | SIA-R05 | Tetap |
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali | SIA-R06 | Tetap |
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | SIA-R07 | Baru |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | SIA-R08, SIA-R12 | Baru |
| SIA-UC09 | Lihat KHS | Mahasiswa | SIA-R09, SIA-R12 | Baru |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | SIA-R10 | Baru |
| SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |
| SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |
| SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |

# Generalization Aktor
| Aktor Umum | Aktor Khusus | Fungsi yang Diwarisi | Alasan Pemodelan |
|---|---|---|---|
| Civitas Akademika | Mahasiswa | Melihat kalender akademik | Mahasiswa termasuk bagian dari civitas akademika sehingga dapat menggunakan fungsi melihat kalender akademik. |
| Civitas Akademika | Dosen | Melihat kalender akademik | Dosen termasuk bagian dari civitas akademika sehingga dapat menggunakan fungsi melihat kalender akademik. |

# Generalization Use Case 
| Use Case Umum | Use Case Khusus | Perilaku Pembeda |
|---|---|---|
| Kelola Data Mahasiswa | Tambah Data Mahasiswa | Admin Akademik menambahkan data mahasiswa baru ke dalam sistem. |
| Kelola Data Mahasiswa | Ubah Data Mahasiswa | Admin Akademik mengubah data mahasiswa yang sudah tersimpan di dalam sistem. |
| Kelola Data Mahasiswa | Hapus Data Mahasiswa | Admin Akademik menghapus data mahasiswa yang sudah tidak diperlukan dari sistem. |

# Tabel Collaboration
| ID Collaboration | Nama Collaboration | Use Case yang Direalisasikan |
|---|---|---|
| SIA-CO01 | Input Nilai Mata Kuliah | SIA-UC08 — Input Nilai Mata Kuliah |
| SIA-CO02 | Lihat KHS | SIA-UC09 — Lihat KHS |





