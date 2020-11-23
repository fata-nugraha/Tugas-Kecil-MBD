# Tugas Kecil IF3140 Manajemen Basis Data
Release: 24 November 2020

Deadline: 1 Desember 2020

Tugas bersifat individu

Modul 0:
1. Buat akun baru di https://scalegrid.io/, emailnya bebas (bisa menggunakan [yopmail](http://www.yopmail.com/en/) kalau perlu)
2. Buat deployment postgresql baru<br><br>
  Cloud profile (optional, recommended): AWS Singapore / Azure Singapore / GCP asia-southeast2 (Jakarta)<br>
  Firewall: Set ke 0.0.0.0/0, lalu klik "Ignore and Proceed"<br>
  Opsi lainnya dapat diabaikan<br>
  Setup deployment butuh waktu sekitar 30-45 menit<br>

Modul 1 (user admin, bisa menggunakan admin default, tidak perlu membuat user baru):
1. Buat database __mbd__ lalu buat tabel __penilaian__ (nim int, nama varchar, nilai int, indeks varchar)
2. Insert nim dan nama Anda dengan nilai 0 dan indeks '' (empty string)
3. Buat user mahasiswa, dosen, asisten1, asisten2, dan asisten3 dengan password __mbd__
4. User mahasiswa hanya dapat melihat nim, nama, dan indeks
5. User dosen dapat melihat semua kolom serta mengedit nilai dan indeks

Modul 2 (user dosen):
1. __Dosen__ membuat role asisten, yang dapat melihat nim, nama, dan nilai serta mengedit nilai
2. __Dosen__ memberikan role asisten ke user asisten1, asisten2, dan asisten3

Modul 3 (user asisten2):
1. Asisten2 memberikan nilai 100 untuk Anda
2. Tunjukkan nilai yang telah berubah

Modul 4 (user dosen):
1. __Dosen__ mencabut akses pada tabel penilaian dari asisten2
2. Tunjukkan bahwa asisten2 sudah tidak memiliki akses pada tabel penilaian

Laporan: 
1. Cover laporan yang berisi kode mata kuliah, nama mata kuliah, judul tugas, logo ITB, nama dan NIM Anda
2. Host deployment postgresql (tidak ada host -> nilai 0)
3. Untuk modul 1-4, tunjukkan bahwa user yang menjalankan query adalah user yang sesuai (dapat menggunakan \conninfo). Tuliskan juga query yang Anda gunakan untuk setiap langkah dan hasil eksekusinya

Format nama file laporan IF3140_TucilMBD_K0X_NIM, upload ke https://driveuploader.com/upload/l5oPYUzW6G/<br>
Selain dicantumkan di laporan, submit juga host ke https://docs.google.com/spreadsheets/d/1F5jI_V2VN7ifs-UbFBqc4ngKPBg2QUjuM1jnchyFzHw/edit

Note: Penilaian akan dilakukan dengan bantuan script, file terlampir adalah __bagian__ dari script yang akan digunakan. Pastikan Anda mengikuti petunjuk yang tersedia dengan baik agar tidak ada kesalahan teknis saat proses penilaian
