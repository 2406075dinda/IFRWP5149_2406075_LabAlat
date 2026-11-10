# Deskripsi Skenario
Dosen pengampu memasukkan nilai mata kuliah mahasiswa. Sistem menyimpan nilai dan memeriksa kelengkapannya. Jika nilai belum lengkap, dosen melengkapi nilai yang masih kosong. Jika nilai lengkap, Admin Akademik memeriksa dan mengesahkan nilai. Setelah nilai disahkan, sistem menyiapkan publikasi hasil studi, lalu menerbitkan KHS pada portal akademik dan mengirim pemberitahuan hasil studi kepada mahasiswa secara paralel. Setelah keduanya selesai, mahasiswa melihat KHS yang hanya memuat nilai yang sudah dipublikasikan.

# Tabel kebutuhan
| ID | Kebutuhan |
|---|---|
| SIA-R08 | Dosen dapat menginput nilai mata kuliah yang diampunya |
| SIA-R09 | Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan |
| SIA-R12 | Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS (SIA-CO01 dan SIA-CO02; tidak digambar pada activity diagram) |

Kebutuhan SIA-R01 sampai SIA-R07 dan SIA-R10, SIA-R11 tidak dimodelkan pada activity diagram ini; rujuk ke Jobsheet Pertemuan 2, 3, dan 4.

# Batas dan asumsi
- Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
- Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut.
- KHS hanya menampilkan nilai yang sudah dipublikasikan.
- Nilai yang belum lengkap tidak dilanjutkan ke pengesahan sampai dosen melengkapinya.
- Pengesahan Admin Akademik, penyiapan publikasi, penerbitan KHS, dan pemberitahuan hasil studi adalah unsur proses baru dari ketentuan Jobsheet P06 dan tidak ada pada tabel skenario P05.
- Collaboration tidak digambar sebagai action atau swimlane.
- Pembayaran dan implementasi basis data berada di luar tugas.

# Identifikasi Aktor
| Aktor | Tujuan Terhadap Sistem |
|---|---|
| Dosen | Memasukkan dan melengkapi nilai mata kuliah yang diampu. |
| Admin Akademik | Memeriksa dan mengesahkan nilai sebelum dipublikasikan. |
| Mahasiswa | Melihat KHS dengan nilai yang sudah dipublikasikan. |
| Sistem (swimlane) | Menyimpan nilai, menyiapkan publikasi, menerbitkan KHS, dan mengirim pemberitahuan. |

# Katalog Use Case
| ID Use Case | Nama Use Case | Aktor | Kebutuhan |
|---|---|---|---|
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | SIA-R08 |
| SIA-UC09 | Lihat KHS | Mahasiswa | SIA-R09 |

# Relasi Include dan Extend
SIA-UC08 dan SIA-UC09 tidak memiliki relasi include maupun extend. Percabangan pada activity diagram digambar sebagai decision Nilai sudah lengkap? dengan guard [lengkap] dan [belum lengkap]. Dua proses yang berjalan bersamaan digambar sebagai satu pasang fork dan join. Collaboration SIA-CO01 dan SIA-CO02 hanya disebut sebagai keterangan, tanpa langkah kegiatan.

# Penelusuran action ke langkah tabel P05
Sumber: `P05_2406075_SIA_skenario_v01.drawio` (tidak diubah).

| Action pada diagram | Swimlane | Sumber langkah P05 | Catatan |
|---|---|---|---|
| Mengisi nilai mahasiswa pada kolom nilai | Dosen | SIA-UC08 langkah 5 | |
| Menyimpan nilai | Sistem | SIA-UC08 langkah 8 | |
| Decision Nilai sudah lengkap? | Sistem | SIA-UC08 langkah 6, 11, 12 | [lengkap] dan [belum lengkap] |
| Melengkapi nilai yang masih kosong | Dosen | SIA-UC08 langkah 11 dan 12 | langkah 12 adalah permintaan sistem; tindak lanjut dosen digambar sebagai action Dosen sesuai ketentuan tugas |
| Memeriksa dan mengesahkan nilai | Admin Akademik | Tidak ada di P05 | unsur proses baru (Jobsheet P06, Langkah 2) |
| Menyiapkan publikasi hasil studi | Sistem | Tidak ada di P05 | unsur proses baru (Jobsheet P06, Langkah 4) |
| Menerbitkan KHS pada portal akademik | Sistem | Tidak ada di P05 | unsur proses baru, paralel (fork) |
| Mengirim pemberitahuan hasil studi kepada mahasiswa | Sistem | Tidak ada di P05 | unsur proses baru, paralel (fork) |
| Melihat KHS | Mahasiswa | SIA-UC09 langkah 1 sampai 4 | KHS hanya memuat nilai yang sudah dipublikasikan |

# Catatan kesesuaian
- Urutan: di P05 pemeriksaan kelengkapan (langkah 6) terjadi sebelum penyimpanan (langkah 8). Ketentuan P06 menaruh decision kelengkapan setelah nilai disimpan, dan diagram mengikuti P06.
- Alternatif P05 langkah 9 dan 10 (nilai di luar rentang ditolak) tidak digambar karena ketentuan P06 hanya mewajibkan satu decision kelengkapan nilai.
