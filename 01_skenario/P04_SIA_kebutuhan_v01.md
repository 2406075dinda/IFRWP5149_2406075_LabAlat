# Tabel kebutuhan 
| ID | Kebutuhan Tugas |
|---|---|
| SIA-R07 | Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik. |
| SIA-R08 | Dosen dapat menginput nilai mata kuliah yang diampunya. |
| SIA-R09 | Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan. |
| SIA-R10 | Admin Akademik dapat mengelola data mahasiswa. |
| SIA-R11 | Pengelolaan data mahasiswa terdiri dari tiga bentuk khusus: tambah, ubah, dan hapus data mahasiswa. |
| SIA-R12 | Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS. |

# Uji Konsistensi, Review, dan Revisi
- Situasi A: Mahasiswa melihat kalender akademik tanpa garis asosiasi langsung dari Mahasiswa.
Hal ini tetap benar karena Mahasiswa merupakan bagian dari Civitas Akademika. Jadi, Mahasiswa bisa melihat kalender akademik melalui hubungan generalisasi aktor.

- Situasi B: Dosen yang bukan pengampu mencoba menginput nilai.
Sistem harus menolak proses input nilai karena dosen tersebut tidak mengampu mata kuliah yang dipilih. Nilai hanya bisa diinput oleh dosen yang mengampu mata kuliah tersebut.

- Situasi C: Admin Akademik menghapus data mahasiswa yang masih memiliki data akademik aktif.
Sistem harus menolak penghapusan data mahasiswa karena masih memiliki data akademik aktif. Data mahasiswa tetap disimpan agar informasi akademiknya tidak hilang.