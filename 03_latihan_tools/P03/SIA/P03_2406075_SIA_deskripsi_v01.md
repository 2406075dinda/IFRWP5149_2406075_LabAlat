# Deskripsi Use Case SIA

## SIA-UC01 — Ajukan KRS

| Elemen                | Deskripsi 
|---------------------- |-----------------------------------
| Tujuan                | Menyimpan pengajuan KRS mahasiswa. 
| Aktor utama           | Mahasiswa 
| Sumber kebutuhan      | SIA-R03 
| Pemicu                | Mahasiswa memilih menu pengajuan KRS. 
| Prasyarat             | Mahasiswa telah login dan data mata kuliah, prasyarat, serta jadwal tersedia. 
| Pascakondisi berhasil | KRS tersimpan dengan status menunggu persetujuan dosen wali. 
| Pascakondisi gagal    | Pengajuan KRS tidak berhasil disimpan. 
| Include               | SIA-UC02 — Validasi KRS 
| Extension point       | Bukti pengajuan tersedia. 
| Extend                | SIA-UC03 jika mahasiswa memilih mengunduh bukti. 

|Alur utama             | Mahasiswa memilih mata kuliah, mengirim KRS, sistem memvalidasi, lalu menyimpan KRS jika valid.
|Alur alternatif        | Jika validasi gagal, pengajuan tidak berhasil disimpan. Mahasiswa dapat memilih mengunduh bukti setelah pengajuan berhasil.

## SIA-UC02 — Validasi KRS

| Elemen           | Deskripsi 
|--------------------------------------
| Tujuan           | Memastikan pengajuan KRS memenuhi ketentuan. 
| Aktor utama      | Sistem 
| Sumber kebutuhan | SIA-R04 
| Pemicu           | Mahasiswa mengirim pengajuan KRS. 
| Prasyarat        | Data mata kuliah, prasyarat, dan jadwal tersedia. 
| Pascakondisi berhasil | KRS lolos pemeriksaan kelengkapan, prasyarat, dan benturan jadwal. 
| Pascakondisi gagal | KRS tidak lolos validasi dan tidak berhasil disimpan. 
| Include           | Tidak ada. 
| Extension point   | Tidak ada. 
| Extend            | Tidak ada. 

|Alur utama         |Sistem memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal.
|Alur alternatif    | Jika salah satu pemeriksaan gagal, validasi dinyatakan gagal.

## SIA-UC03 — Unduh Bukti Pengajuan KRS

| Elemen        | Deskripsi 
|------------------------------
| Tujuan        | Mendapatkan bukti pengajuan KRS. 
| Aktor utama   | Mahasiswa 
| Sumber kebutuhan | SIA-R05 
| Pemicu        | Mahasiswa memilih mengunduh bukti saat konfirmasi pengajuan. 
| Prasyarat     | KRS berhasil disimpan dan bukti tersedia. 
| Pascakondisi berhasil | Bukti pengajuan berhasil diunduh. 
| Pascakondisi gagal | Bukti tidak berhasil diunduh, tetapi KRS tetap tersimpan. 
| Include       | Tidak ada. 
| Extension point | Tidak ada. 
| Extend        | Memperluas SIA-UC01 dengan kondisi [mahasiswa memilih mengunduh bukti]. 

|Alur utama     | Mahasiswa memilih unduh bukti, lalu sistem menyediakan bukti pengajuan.
|Alur alternatif| Jika unduhan gagal, KRS tetap tersimpan.


## SIA-UC04 — Proses Keputusan KRS

| Elemen           | Deskripsi 
|--------------------------
| Tujuan           | Memproses persetujuan atau penolakan KRS. 
| Aktor utama      | Dosen wali 
| Sumber kebutuhan | SIA-R06 
| Pemicu           | Dosen wali memilih pengajuan KRS untuk diproses. 
| Prasyarat        | KRS telah tersimpan dan menunggu persetujuan. 
| Pascakondisi berhasil | Keputusan dan catatan dosen wali tersimpan. 
| Pascakondisi gagal | Keputusan belum berhasil diproses. 
| Include | Tidak ada. 
| Extension point  | Tidak ada. 
| Extend           | Tidak ada.

|Alur utama        | Dosen wali memeriksa KRS, menyetujui atau menolak, lalu memberikan catatan keputusan.
|Alur alternatif   | Jika keputusan gagal diproses, keputusan belum tercatat.