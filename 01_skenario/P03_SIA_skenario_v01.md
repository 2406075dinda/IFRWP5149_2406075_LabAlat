# Deskripsi Skenario
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap 
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, 
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, 
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen 
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih 
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS 
dan memberikan catatan keputusan.

# Tabel kebutuhan
|ID       | Kebutuhan
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah |
| SIA-R02 | Admin akademik dapat mengelola jadwal kuliah |
| SIA-R03 | Mahasiswa dapat mengajukan KRS |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian pengajuan |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
| SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS |

# Batas dan asumsi 
• Pengguna telah terautentikasi. 
• Data mata kuliah, prasyarat, dan jadwal tersedia. 
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan. 
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan. 
• KRS tersimpan belum berarti disetujui. 
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar 
tugas. 

# Identifikasi Aktor

| Aktor         | Tujuan Terhadap Sistem 
|---            |--------------------------                        
| Mahasiswa     | Mengajukan KRS dan mengunduh bukti pengajuan jika diperlukan. 
| Dosen wali    | Memproses persetujuan atau penolakan KRS dan memberikan catatan keputusan. 

# Katalog Use Case

| ID Use Case | Nama Use Case             | Aktor       | Kebutuhan 
|---          |---                        |---          |---
| SIA-UC01    | Ajukan KRS                | Mahasiswa   | SIA-R03 |
| SIA-UC02    | Validasi KRS              | Sistem      | SIA-R04 |
| SIA-UC03    | Unduh bukti pengajuan KRS | Mahasiswa   | SIA-R05 |
| SIA-UC04    | Proses keputusan KRS      | Dosen wali  | SIA-R06 |

# Relasi Include

Use case Ajukan KRS (SIA-UC01) memiliki relasi <<include>> dengan Validasi KRS (SIA-UC02), karena setiap pengajuan KRS harus melalui validasi kelengkapan, prasyarat mata kuliah, dan benturan jadwal.

Arah panah `<<include>>` adalah dari Ajukan KRS menuju Validasi KRS.

# Relasi Extend

Use case Unduh bukti pengajuan KRS (SIA-UC03) memiliki relasi <<extend>> terhadap Ajukan KRS (SIA-UC01), dengan kondisi [mahasiswa memilih mengunduh bukti].

Extension point: Bukti pengajuan tersedia.

Unduh bukti bersifat opsional dan tidak menjadi syarat keberhasilan pengajuan KRS.

Arah panah <<extend>> adalah dari Unduh bukti pengajuan KRS menuju Ajukan KRS.