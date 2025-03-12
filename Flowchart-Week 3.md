# SISTEM OPERASI
# Minggu ke-3 : Selasa, 4 Maret 2025

 
# Oleh :
# Mey Risa Handayani
# D3 Teknik Informatika (A) PENS LA
# NRP 3124521011

# Dosen Pengampu :
# Dr Ferry Astika Saputra ST, M.Sc
# NIP : 197708232001121002


# POLITEKNIK ELEKTRONIKA NEGERI SURABAYA
# PSDKU LAMONGAN
# TAHUN 2025

## Flowchart ini menggambarkan proses booting pada komputer, mulai dari saat komputer dinyalakan hingga siap digunakan. Berikut adalah penjelasan dari setiap langkahnya:

## 1. Start
Proses booting dimulai ketika komputer dinyalakan.

## 2. Power-On Self Test (POST)
Sistem menjalankan tes awal untuk memeriksa perangkat keras (RAM, CPU, GPU, dll.).

## 3. Apakah POST berhasil?
Jika POST gagal: komputer menampilkan error atau kode beep untuk menunjukkan kesalahan perangkat keras.
Jika POST berhasil: proses booting berlanjut.

## 4. Load BIOS/UEFI
BIOS/UEFI dimuat untuk menginisialisasi perangkat keras dan mencari bootloader.

## 5. Cari Bootloader (MBR/GPT)
BIOS/UEFI mencari lokasi bootloader pada penyimpanan utama (Master Boot Record atau GUID Partition Table).

## 6. Load Bootloader (GRUB, Windows Boot Manager, dll.)
Bootloader seperti GRUB (Linux) atau Windows Boot Manager dimuat untuk menyiapkan sistem operasi.

## 7. Load OS ke Memory
Sistem operasi mulai dimuat ke dalam RAM untuk eksekusi.

## 8. Inisialisasi Kernel dan Driver
Kernel sistem operasi diinisialisasi dan driver perangkat keras dimuat agar sistem dapat berjalan dengan baik.

## 9. Load User Interface (GUI/CLI)
Antarmuka pengguna (baik GUI seperti Windows/Linux Desktop atau CLI seperti Terminal) dimuat.

## 10. Komputer Siap Digunakan
Sistem operasi telah sepenuhnya dimuat dan komputer siap digunakan.

## 11. End
Proses booting selesai.


![image](https://github.com/user-attachments/assets/649615e5-538b-4c7d-ae1d-c510b83a585d)
