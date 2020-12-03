# Tugas Kecil IF3140 Manajemen Basis Data
Release: Selasa, 24 November 2020

Deadline: Kamis, 3 Desember 2020 23:59 (ada problem di scalegrid, deadline diundur)

Tugas bersifat individu

Modul 0.1:
1. Masuk ke https://portal.azure.com/ menggunakan akun NIM@office.itb.ac.id
1a. Pilih Access student benefit jika diminta (tidak perlu credit card)
2. Search virtual machine, lalu pilih add -> virtual machine
3. Create new resource group (nama bebas), virtual machine name (bebas), region southeast-asia (optional, recommended), image Ubuntu Server 18.04 LTS - Gen1, size B1s
4. Authentication type password, <username> dan <password> bebas (akan dipakai)
5. Public inbound ports: Allow selected ports, pilih yang ssh (22)
6. Review + create, lalu klik Create

Modul 0.2:
1. Klik Go to resource (atau klik home lalu buka VMnya di recent resources), klik IP address lalu ubah menjadi static
2. Buka page VM lagi, di Settings -> Networking, Add inbound port rule, Destination port ranges 5432, name bebas, klik Add
3. Di command prompt (Windows)/terminal (Linux), `ssh <username>@<IP address>` untuk masuk ke VM, lalu input password
4. Copy-paste script yang ada di https://www.postgresql.org/download/linux/ubuntu/ di VM
5. `sudo nano /etc/postgresql/13/main/pg_hba.conf` lalu tambahkan `host all all 0.0.0.0/0 md5` di bagian akhir file, Ctrl+X -> y -> enter untuk save file
6. `sudo nano /etc/postgresql/13/main/postgresql.conf`, klik f6 (search), cari listen_address, remove # di awal line lalu ganti `localhost` menjadi `*`
7. `sudo service postgresql restart`
8. `sudo -u postgres psql` untuk masuk ke database as admin
9. Kerjakan modul 1-4, lalu coba jalankan script python dengan host `<IP address>`

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
__Laporan yang disubmit setelah deadline tidak akan diperiksa__<br>
Selain dicantumkan di laporan, submit juga host ke https://forms.gle/bGAoDLsaw4SB6EyA6<br>
Pastikan host yang disubmit ke form bisa diconnect dengan script python di repo ini

Note: Penilaian akan dilakukan dengan bantuan script, file terlampir adalah __bagian__ dari script yang akan digunakan. Pastikan Anda mengikuti petunjuk yang tersedia dengan baik agar tidak ada kesalahan teknis saat proses penilaian
