| Nama                    | NIM        | Kelas   | Matkul            |
|-------------------------|------------|---------|-------------------|
| Revo Permana Adzi       | 312310371  | TI.23.A4| Pemrograman Web 2 |

Praktikum 1-6

1. Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache
klik Config -> PHP.ini

![Screenshot 2025-03-21 123847](https://github.com/user-attachments/assets/b8ba7a44-51a2-4c61-949f-abae1f2d7e90)


2. Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan.
Kemudian simpan kembali filenya dan restart Apache web server.

![Screenshot 2025-03-21 124027](https://github.com/user-attachments/assets/3fe5a173-86da-4403-a2c7-a197062a1ba8)

3. Instalasi Codeigniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual
dan menggunakan composer.

![Screenshot 2025-03-21 124734](https://github.com/user-attachments/assets/2273914b-d553-4bb5-b545-a140c6b133c5)

4. Menjalankan CLI (Command Line Interface)
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses
CLI buka terminal/command prompt.

![Screenshot 2025-03-21 124930](https://github.com/user-attachments/assets/ada133ea-44fd-491e-87de-365eecdd17cf)

Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat
(xampp/htdocs/lab11_ci/ci4/)

5. Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah:
   **PHP SPARK**

![image](https://github.com/user-attachments/assets/b88daf73-e414-4349-b54b-354aadb92ad9)

6. Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui
pesan error apabila terjadi kesalahan dalam membuat kode program.
Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan
kesalahan seperti berikut.

![image](https://github.com/user-attachments/assets/b5e6e606-9b78-424b-8cf1-edb1b6f72e0f)

7. Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya,
maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment
variable CI_ENVIRINMENT menjadi development.

![image](https://github.com/user-attachments/assets/4ae40147-e188-46e9-b14b-ffd0e33eed01)

Ubah nama file env menjadi .env kemudian buka file tersebut dan ubah nilai variable
CI_ENVIRINMENT menjadi development.

![image](https://github.com/user-attachments/assets/457e7a6a-474d-4f59-8208-f1bc1cdb33be)

Contoh error yang terjadi. Untuk mencoba error tersebut, ubah kode pada file
app/Controller/Home.php hilangkan titik koma pada akhir kode.

![image](https://github.com/user-attachments/assets/ed11d490-dc4f-431f-8d8e-ce1fd94dce35)

8. Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router untuk
meudian oleh router tesebut diarahkan ke Controller.
Router terletak pada file **app/config/Routes.php**

![image](https://github.com/user-attachments/assets/d4492232-bce8-43f8-a232-fce17fdce80f)

9. Membuat Route Baru.
Tambahkan kode berikut di dalam **Routes.php**

$routes->get('/about', 'Page::about');
$routes->get('/contact', 'Page::contact');
$routes->get('/faqs', 'Page::faqs');

![image](https://github.com/user-attachments/assets/e0df964a-7992-4fa7-964f-61993655aab0)

Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah
berikut.

![image](https://github.com/user-attachments/assets/97f99f5e-7f20-43a0-925a-75d44edcb3d6)

Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url
http://localhost:8080/about

![Screenshot 2025-03-21 131531](https://github.com/user-attachments/assets/2f3edd4f-6569-43a8-9800-b6273c99b5bc)

Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak
ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu Contoller yang
sesuai dengan routing yang dibuat yaitu Contoller Page.

10. Membuat Controller
Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama **page.php** pada
direktori Controller kemudian isi kodenya seperti berikut.

![image](https://github.com/user-attachments/assets/c299574b-ce23-460a-a56d-3db282e82ac3)

Selanjutnya refresh Kembali browser, maka akan ditampilkan hasilnya yaotu halaman sudah
dapat diakses.

![Screenshot 2025-03-21 132900](https://github.com/user-attachments/assets/3f5987fd-8fe8-4cf8-8a19-e067cc3fef12)

11. Auto Routing
Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute
dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true menjadi false.

Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan
alamat: http://localhost:8080/page/tos

![image](https://github.com/user-attachments/assets/31cf84ba-697f-443b-87e3-dd2789cc8637)

12. Membuat View
Selanjutnya dalam membuat view untuk tampilan web agar lebih menarik. Buat file baru
dengan nama **about.php** pada direktori view **(app/view/about.php)** kemudian isi kodenya
seperti berikut.

![image](https://github.com/user-attachments/assets/daff301b-6d8d-4be0-a055-325edffa0e96)

Ubah method about pada class Controller Page menjadi seperti berikut:

<img width="627" alt="image" src="https://github.com/user-attachments/assets/9d95d4ac-d564-4f7e-a5a0-3434f6ea8e52" />

Kemudian lakukan refresh pada halaman tersebut.

![image](https://github.com/user-attachments/assets/b285993b-bf83-449c-a4d4-e283d25cb86c)

13. Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada
codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css
dan javascript terletak pada direktori public.
Buat file css pada direktori public dengan nama style.css

![image](https://github.com/user-attachments/assets/d4099607-3343-4ae5-b1e7-c972aed2c39b)

Kemudian buat folder template pada direktori view kemudian buat file **header.php**h dan
**footer.php**

![image](https://github.com/user-attachments/assets/3fb3cbc9-7f2f-4e8f-bbec-7a1abcc84c65)

File **app/view/template/footer.php**

![Screenshot 2025-03-21 134623](https://github.com/user-attachments/assets/ec607eeb-4662-459a-b9cb-64b2fe96b717)

Kemudian ubah file **app/view/about.php** seperti berikut.

![image](https://github.com/user-attachments/assets/cd5c4862-8a4b-4fab-a187-83a853bfbc5b)

Selanjutnya refresh tampilan pada alamat http://localhost:8080/about

![image](https://github.com/user-attachments/assets/6dbf8d4a-a53f-475c-8a27-f41291836329)

14. Membuat database di my sql dengan nama lab_ci4

![image](https://github.com/user-attachments/assets/9eb909fb-33ef-4c69-ae6c-4359e2a0e332)

setelah membuat data base, lalu membuat tablenya dengan nama artikel

![image](https://github.com/user-attachments/assets/b20b1606-c8c0-420a-a778-1812ae5b2cc7)

15. Konfigurasi koneksi database
Selanjutnya membuat konfigurasi untuk menghubungkan dengan database server. Konfigurasi
dapat dilakukan dengan du acara, yaitu pada file **app/config/database.php** atau menggunakan
file **.env.** Pada praktikum ini kita gunakan konfigurasi pada file **.env.**

![image](https://github.com/user-attachments/assets/298f0c1b-66c5-4285-9f2e-1f6380750355)

16. Membuat Model
Selanjutnya adalah membuat Model untuk memproses data Artikel. Buat file baru pada
direktori app/Models dengan nama **ArtikelModel.php

![image](https://github.com/user-attachments/assets/50b97124-a21c-4b39-b0bd-a11d053fbaba)

17. Membuat Controller
Buat Controller baru dengan nama **Artikel.php** pada direktori app/Controllers.

![image](https://github.com/user-attachments/assets/898d6d00-d37a-4437-b348-2320f0c9e88c)

18. Membuat View
Buat direktori baru dengan nama artikel pada direktori app/views, kemudian buat file baru
dengan nama **index.php.**

![image](https://github.com/user-attachments/assets/daac512a-cc9f-4006-9f8a-d8381b91b38e)

Selanjutnya buka browser kembali, dengan mengakses url http://localhost:8080/artikel

![image](https://github.com/user-attachments/assets/2095cbd0-8697-4dce-8fa2-9ec28b9d4663)

Belum ada data yang diampilkan. Kemudian coba tambahkan beberapa data pada database agar
dapat ditampilkan datanya.

**INSERT INTO artikel (judul, isi, slug) VALUE
('Artikel pertama', 'Lorem Ipsum adalah contoh teks atau dummy dalam industri percetakan dan penataan huruf atau typesetting. Lorem Ipsum telah
menjadi standar contoh teks sejak tahun 1500an, saat seorang tukang cetak
yang tidak dikenal mengambil sebuah kumpulan teks dan mengacaknya untuk
menjadi sebuah buku contoh huruf.', 'artikel-pertama'),
('Artikel kedua', 'Tidak seperti anggapan banyak orang, Lorem Ipsum
bukanlah teks-teks yang diacak. Ia berakar dari sebuah naskah sastra latin
klasik dari era 45 sebelum masehi, hingga bisa dipastikan usianya telah
mencapai lebih dari 2000 tahun.', 'artikel-kedua');**

Refresh kembali browser, sehingga akan ditampilkan hasilnya.

![image](https://github.com/user-attachments/assets/c51bdd8e-deba-4725-9e59-721aa7cee15e)

19. Membuat Tampilan Detail Artikel
Tampilan pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda.
Tambahkan fungsi baru pada Controller Artikel dengan nama **view**().

![image](https://github.com/user-attachments/assets/f407fc46-c2e9-48f7-9dac-7544ffc0ffd0)

20. Membuat View Detail
Buat view baru untuk halaman detail dengan nama **app/views/artikel/detail.php.**

![image](https://github.com/user-attachments/assets/52dcb932-f354-47e4-adfc-6c3d3d4c573e)

21. Membuat Routing untuk artikel detail
Buka Kembali file **app/config/Routes.php**, kemudian tambahkan routing untuk artikel detail.

![image](https://github.com/user-attachments/assets/96a83682-0286-4a77-ab61-74fd887711eb)

![image](https://github.com/user-attachments/assets/960ded60-038f-4163-917b-e92d9c3c165a)

22. Membuat Menu Admin
Menu admin adalah untuk proses CRUD data artikel. Buat method baru pada Controller
Artikel dengan nama **admin_index()**.

![image](https://github.com/user-attachments/assets/e857ac11-fafe-40d2-b0ec-3d3094c0a940)

Selanjutnya buat view untuk tampilan admin dengan nama **admin_index.php**

![Screenshot 2025-03-23 135513](https://github.com/user-attachments/assets/7a5e3ccf-89eb-4699-88a3-36317d84c097)

![Screenshot 2025-03-23 135534](https://github.com/user-attachments/assets/1a872862-e42b-4843-a3c1-443e099ffd8d)

![Screenshot 2025-03-23 135750](https://github.com/user-attachments/assets/bd54a369-8ce0-4851-bdc2-5d679efaf666)

![Screenshot 2025-03-23 135806](https://github.com/user-attachments/assets/4af20293-7339-4195-8d14-06a92594ddc6)

Tambahkan routing untuk menu admin seperti berikut:

![image](https://github.com/user-attachments/assets/03d240eb-467b-4508-a385-7051320b167f)

Akses menu admin dengan url http://localhost:8080/admin/artikel

![Screenshot 2025-03-23 140106](https://github.com/user-attachments/assets/a29dda68-4955-46d5-952d-79e928701737)

23. Menambah Data Artikel
Tambahkan fungsi/method baru pada Controller Artikel dengan nama add().

![image](https://github.com/user-attachments/assets/021a3384-b68b-4b3a-b8ac-4c670e476005)

Kemudian buat view untuk form tambah dengan nama **form_add.php**

![Screenshot 2025-03-23 140417](https://github.com/user-attachments/assets/60aa76cb-c0f2-4b26-a3b3-2728e6ca4a77)

![image](https://github.com/user-attachments/assets/c4523463-46d7-4213-af73-b958cd279108)

24. Mengubah Data
Tambahkan fungsi/method baru pada Controller Artikel dengan nama **edit().**

![image](https://github.com/user-attachments/assets/d8684394-4097-4550-be78-cdb8857ad6bb)

Kemudian buat view untuk form tambah dengan nama **form_edit.php**

![image](https://github.com/user-attachments/assets/e576d3f0-5785-4f69-9129-1945e790ad72)

![image](https://github.com/user-attachments/assets/300bb226-325c-4de1-9481-aa998e38b4c7)

25. Menghapus Data
Tambahkan fungsi/method baru pada Controller Artikel dengan nama **delete()**.

![image](https://github.com/user-attachments/assets/276a3ee5-2b3a-4470-8a1d-a662d94fcb91)

26. Membuat Layout Utama
Buat folder **layout** di dalam **app/Views/**
Buat file **main.php** di dalam folder **layout** dengan kode berikut:

![image](https://github.com/user-attachments/assets/c3ea7d25-7e97-4c06-a53a-26b3a2acaa03)

![image](https://github.com/user-attachments/assets/0051ef7e-24f6-4740-97c2-96f3ec10341f)

27. Modifikasi File View
Ubah **app/Views/home.php** agar sesuai dengan layout baru:

![image](https://github.com/user-attachments/assets/e5a2fbb3-064e-470c-98b0-aafe29a15e31)

28. Membuat Class View Cell
Buat folder **Cells** di dalam **app/**
Buat file **ArtikelTerkini.php** di dalam **app/Cells/** dengan kode berikut:

![image](https://github.com/user-attachments/assets/6be0740b-4e46-430b-bab6-20207e85e7d5)

29. Membuat View untuk View Cell
Buat folder components di dalam **app/Views/**
Buat file **artikel_terkini.php** di dalam **app/Views/components/** dengan kode berikut:

![image](https://github.com/user-attachments/assets/d250d040-7b4e-4ad9-9d63-c59293f2ce9c)

30. Menambahkan tanggal
tujuanya agar mendapatkan data aertikel yang baru di ubah

![image](https://github.com/user-attachments/assets/313b69f7-f993-4487-82ce-22c9817fb689)

contohnya seperti ini :

![image](https://github.com/user-attachments/assets/88d73672-4819-47fa-8d32-1c22c1b740a7)

Apa manfaat utama dari penggunaan View Layout dalam pengembangan aplikasi?
jawab : 
1. Struktur yang Terorganisir
  - Memudahkan pengaturan elemen UI dengan tata letak yang rapi dan terstruktur.

2. Responsivitas yang Lebih Baik
  - Memastikan tampilan UI menyesuaikan dengan berbagai ukuran layar dan orientasi perangkat.

3. Pemeliharaan Kode yang Lebih Mudah
  - Dengan pemisahan tata letak dan logika bisnis, perubahan UI lebih mudah dilakukan tanpa mengganggu fungsionalitas aplikasi.
    
4. Penggunaan Ulang Komponen
  - Layout dapat digunakan kembali di berbagai bagian aplikasi, mengurangi redundansi kode.

5. Kinerja yang Lebih Optimal
  - Beberapa jenis layout dioptimalkan untuk performa yang lebih baik, seperti ConstraintLayout di Android yang mengurangi jumlah view hierarchy.

Jelaskan perbedaan antara View Cell dan View biasa.
jawab : 
![image](https://github.com/user-attachments/assets/3f08a236-4d3c-4d34-ab79-991e4f154339)

31. Membuat tabel database dengan nama Tabel Login

![image](https://github.com/user-attachments/assets/7a3d1c57-d948-4f9b-859b-f9fd89b6d1a8)

32. Selanjutnya membuat Tabel User di dalam database yang bernama Tabel Login

![image](https://github.com/user-attachments/assets/6e36de67-5137-48e8-a9c3-a75b9e247af0)

33. Membuat Model User
Selanjutnya adalah membuat Model untuk memproses data Login. Buat file baru pada direktori
app/Models dengan nama **UserModel.php**

![image](https://github.com/user-attachments/assets/d8bff122-14c1-4347-8b46-78d08b66b30f)

34. Membuat Controller User
Buat Controller baru dengan nama User.php pada direktori **app/Controllers**. Kemudian
tambahkan method index() untuk menampilkan daftar user, dan method login() untuk proses
login.

![image](https://github.com/user-attachments/assets/4d10fdd0-2a6f-4d8d-8830-676f70123339)
![image](https://github.com/user-attachments/assets/36405121-2820-46ec-8cb2-8bd42bffcab2)

35. Membuat View Login
Buat direktori baru dengan nama **user** pada direktori **app/views**, kemudian buat file baru
dengan nama **login.php**.

<img width="536" alt="image" src="https://github.com/user-attachments/assets/d65ff64d-6839-4d48-9dd2-7cac74b8517f" />

![image](https://github.com/user-attachments/assets/27388072-98f6-48a4-a13b-96d56d12dda9)

![image](https://github.com/user-attachments/assets/f8ae84cf-4da6-482f-a41a-60e0a8a4644d)

36. Membuat Database Seeder
Database seeder digunakan untuk membuat data dummy. Untuk keperluan ujicoba modul
login, kita perlu memasukkan data user dan password kedaalam database. Untuk itu buat
database seeder untuk tabel user. Buka CLI, kemudian tulis perintah berikut:

![image](https://github.com/user-attachments/assets/586def79-3abb-4c2c-8e2f-12fc6e54c226)

Selanjutnya, buka file **UserSeeder.php** yang berada di lokasi direktori
**/app/Database/Seeds/UserSeeder.php** kemudian isi dengan kode berikut:

![image](https://github.com/user-attachments/assets/a67d0b63-6801-4692-9c22-e2827d62bb8e)

Selanjutnya buka kembali CLI dan ketik perintah berikut:
![image](https://github.com/user-attachments/assets/0e9fbcd7-127f-44f7-8c69-4728dde5ec0b)

37. **Uji Coba Login**
Selanjutnya buka url http://localhost:8080/user/login seperti berikut:

![image](https://github.com/user-attachments/assets/4e439b3a-db78-4b17-859f-9b39bb8fdbf5)

38. Menambahkan Auth Filter
Selanjutnya membuat filer untuk halaman admin. Buat file baru dengan nama **Auth.php** pada
direktori **app/Filters**.

![image](https://github.com/user-attachments/assets/d07d3696-1d62-45b7-89a8-2fbe57c9656b)

39. Selanjutnya buka file **app/Config/Filters.php** tambahkan kode berikut:

![image](https://github.com/user-attachments/assets/ff38aa1a-f381-41c4-a3bc-ba21cce2f165)

40. Selanjutnya buka file **app/Config/Routes.php** dan sesuaikan kodenya.

![image](https://github.com/user-attachments/assets/ebeadfc0-c551-464e-bbee-dab9983d305a)

41. Percobaan Akses Menu Admin
Buka url dengan alamat http://localhost:8080/admin/artikel ketika alamat tersebut diakses
maka, akan dimuculkan halaman login.

![image](https://github.com/user-attachments/assets/cc397952-3dc8-433e-aa26-e78a57ba2bad)

42. Fungsi Logout
Tambahkan method logout pada Controller User seperti berikut:

![image](https://github.com/user-attachments/assets/8697ca0a-b005-4472-9f0a-08356e4598df)

43. Untuk membuat pagination, buka Kembali **Controller Artikel**, kemudian modifikasi kode
pada method **admin_index** seperti berikut.

![image](https://github.com/user-attachments/assets/4e665aff-31e0-4a86-af0e-52f7a533c66e)

44. Kemudian buka file **views/artikel/admin_index.php** dan tambahkan kode berikut
dibawah deklarasi tabel data.

![image](https://github.com/user-attachments/assets/2ae8069c-78b2-4e3e-8f39-0acc4839bf9d)

45. Selanjutnya buka kembali menu daftar artikel, tambahkan data lagi untuk melihat
hasilnya.

<img width="824" alt="image" src="https://github.com/user-attachments/assets/0ac6ab12-3ec8-4b05-b161-eacb440b9cb4" />

46. Membuat Pencarian
Pencarian data digunakan untuk memfilter data.
Untuk membuat pencarian data, buka kembali **Controller Artikel**, pada method
**admin_index** ubah kodenya seperti berikut:

![image](https://github.com/user-attachments/assets/7a5c383d-959c-4029-b415-b8535068befd)

47. Kemudian buka kembali file **views/artikel/admin_index.php** dan tambahkan form
pencarian sebelum deklarasi tabel seperti berikut:

![image](https://github.com/user-attachments/assets/0b7ab4e8-934a-4c55-823a-ad88c89ac05e)

Dan pada link pager ubah seperti berikut.

![image](https://github.com/user-attachments/assets/b9b1133b-95d3-4256-80f9-e188bbbd1b5c)

48. Selanjutnya ujicoba dengan membuka kembali halaman admin artikel, masukkan kata
kunci tertentu pada form pencarian.

![Screenshot 2025-04-22 134919](https://github.com/user-attachments/assets/73fbf013-97b4-4774-9f2c-db6cbdabc1f2)

49. Upload Gambar pada Artikel
Menambahkan fungsi unggah gambar pada tambah artikel.
Buka kembali **Controller Artikel** pada project sebelumnya, sesuaikan kode pada method
add seperti berikut:

![image](https://github.com/user-attachments/assets/37a6fdcb-3f00-4483-a167-814bcf8380f2)

50. Kemudian pada file **views/artikel/form_add.php** tambahkan field input file seperti
berikut.

![image](https://github.com/user-attachments/assets/48b23db0-53fc-4652-8516-523da1cc60cb)

51. Dan sesuaikan tag form dengan menambahkan ecrypt type seperti berikut.

![image](https://github.com/user-attachments/assets/e34fb0ed-2538-4ad8-9361-8c19105484e8)

52. Ujicoba file upload dengan mengakses menu tambah artikel.

![image](https://github.com/user-attachments/assets/a92889b0-bc3e-469b-8fe8-51edcc72e534)


Praktikum 7-10

53. Membuat Tabel Kategori
Kita akan membuat tabel baru bernama `kategori` untuk mengkategorikan artikel.
Struktur Tabel `kategori`:

Jalankan query berikut:
![Screenshot 2025-06-17 101611](https://github.com/user-attachments/assets/48a387d5-78ec-4e41-ba23-c73eced93484)

54. Mengubah Tabel Artikel
Tambahkan foreign key `id_kategori` pada tabel `artikel` untuk membuat relasi dengan tabel 
`kategori`. 
Query untuk menambahkan foreign key:

![image](https://github.com/user-attachments/assets/07770285-6aa2-4d06-82c7-d3f9731abad7)

55. Membuat Model Kategori
Buat file model baru di `app/Models` dengan nama `KategoriModel.php`:

![image](https://github.com/user-attachments/assets/935c14d4-f941-4fa2-9458-5bdf16f55df0)

56. Memodifikasi Model Artikel
Modifikasi `ArtikelModel.php` untuk mendefinisikan relasi dengan `KategoriModel`:

![image](https://github.com/user-attachments/assets/ce339452-0656-4daf-a88c-8f4acd645344)

Menambahkan method `getArtikelDenganKategori()` untuk mengambil data artikel beserta 
nama kategorinya menggunakan join

57. Memodifikasi Controller Artikel
Modifikasi `Artikel.php` untuk menggunakan model baru dan menampilkan data relasi:

![image](https://github.com/user-attachments/assets/1f0c0376-460f-4641-8f99-5d7a9a69b769)

![image](https://github.com/user-attachments/assets/1ccca0a1-56be-46ba-894e-5f81db6628df)

![image](https://github.com/user-attachments/assets/4aaa30dd-035d-482d-9242-a6da1d344378)

![image](https://github.com/user-attachments/assets/a8ab05c9-975a-4e71-a707-0c777a0c7052)

![image](https://github.com/user-attachments/assets/ec7b5a4b-d17e-4da1-8cd4-1e17aa1bbb7b)

![image](https://github.com/user-attachments/assets/02cff5c1-8d92-440f-bbde-c5cf9356b543)

![image](https://github.com/user-attachments/assets/66040985-7704-465c-be37-45c0ec89ed7a)

58. Memodifikasi View
Buka folder view/artikel sesuaikan masing-masing view.
**index.php**

![image](https://github.com/user-attachments/assets/fff913f3-aa5d-4d7b-9890-2f46abb4e30a)

**admin_index.php**

![image](https://github.com/user-attachments/assets/6c98713c-fb44-4f70-be84-b70195c41fb6)

![image](https://github.com/user-attachments/assets/83cad4ec-7c8c-4465-b16c-e80783edfb7b)

![image](https://github.com/user-attachments/assets/9f909071-72e0-4070-be52-025f1fd75166)

![image](https://github.com/user-attachments/assets/d5ad6833-466f-4b36-a528-ab02056c54de)

![image](https://github.com/user-attachments/assets/77f11021-378e-46bd-b490-4fe9a482c0f5)

**form_add.php**

![image](https://github.com/user-attachments/assets/007e1d63-f75b-4720-991e-245eab7d6645)

![image](https://github.com/user-attachments/assets/4c3c2a5f-16ce-4068-b506-f2dc7321fb48)

![image](https://github.com/user-attachments/assets/f08f0878-867d-4bb1-b7e3-9e4d5d7ec436)

**form_edit.php**

![image](https://github.com/user-attachments/assets/bcf71563-8c33-424e-a9fa-0b833ddc0282)

![image](https://github.com/user-attachments/assets/9daab03a-0b06-4ec2-8b6c-2215ccc25aa3)

![image](https://github.com/user-attachments/assets/30fd0aa7-026b-4169-b8f8-9187ba842a69)

59. Testing
Lakukan uji coba untuk memastikan semua fungsi berjalan dengan baik:
• Menampilkan daftar artikel dengan nama kategori.

![Screenshot 2025-06-17 124824](https://github.com/user-attachments/assets/ed3fc36e-1243-4608-bc49-365a25299688)

• Menambah artikel baru dengan memilih kategori.

![Screenshot 2025-06-17 124935](https://github.com/user-attachments/assets/dda950ed-b6cf-4dfc-8db5-9e44e83196bc)

• Mengedit artikel dan mengubah kategorinya.

![Screenshot 2025-06-17 125155](https://github.com/user-attachments/assets/d142f007-d18a-47f2-8f31-017d4bb5cfa7)

• Menghapus artikel.

![Screenshot 2025-06-17 125238](https://github.com/user-attachments/assets/dc08b9f2-3b5e-4a54-a034-232b7de82f4d)

![Screenshot 2025-06-17 125300](https://github.com/user-attachments/assets/014a0912-9848-4b71-bd05-5bbd9faca568)

60. Membuat Model.
Pada modul sebelumnya sudah dibuat ArtikelModel, pada modul ini kita akan
memanfaatkan model tersebut agar dapat diakses melalui AJAX.

61. Membuat AJAX Controller

![image](https://github.com/user-attachments/assets/46c90da8-8852-4a70-9d5d-2e0d27bb0971)

62. Membuat View

![image](https://github.com/user-attachments/assets/89bec5c2-f3e3-4f14-93b8-19b4ab526df1)

![image](https://github.com/user-attachments/assets/e5922213-a54c-43d8-b8b3-4784ba35caca)

![image](https://github.com/user-attachments/assets/3e53ed3f-7178-47d0-8027-a58e612231ca)

![image](https://github.com/user-attachments/assets/ce508026-8ca8-4f8c-8c6c-c7ebe322d0d1)

63. Persiapan
* Pastikan MySQL Server sudah berjalan.
* Buka database `lab_ci4`.
* Pastikan tabel `artikel` dan `kategori` sudah ada dan terisi data.
* Pastikan library jQuery sudah terpasang atau dapat diakses melalui CDN.

64. Modifikasi Controller Artikel
Ubah method `admin_index()` di `Artikel.php` untuk mengembalikan data dalam format
JSON jika request adalah AJAX. (Sama seperti modul sebelumnya)

![image](https://github.com/user-attachments/assets/3e57d9ad-8b23-41e3-90a6-934de1ab3740)

Penjelasan:
• `$page = $this->request->getVar('page') ?? 1;`: Mendapatkan nomor
halaman dari request. Jika tidak ada, default ke halaman 1.
• `$builder->paginate(10, 'default', $page);`: Menerapkan pagination
dengan nomor halaman yang diberikan.
• `$this->request->isAJAX()`: Memeriksa apakah request yang datang adalah
AJAX.
• Jika AJAX, kembalikan data artikel dan pager dalam format JSON.
• Jika bukan AJAX, tampilkan view seperti biasa.

65. Modifikasi View (admin_index.php)
* Ubah view `admin_index.php` untuk menggunakan jQuery.
* Hapus kode yang menampilkan tabel artikel dan pagination secara langsung.
* Tambahkan elemen untuk menampilkan data artikel dan pagination dari AJAX.
* Tambahkan kode jQuery untuk melakukan request AJAX.

![image](https://github.com/user-attachments/assets/2afe6114-97ea-4cc8-90a8-e79bcc9b3e70)

![image](https://github.com/user-attachments/assets/a4b6cf7a-c63a-49ae-a45b-e2c216a2a945)

![image](https://github.com/user-attachments/assets/dc7a12a7-abb3-4179-b387-368887550d1f)

![image](https://github.com/user-attachments/assets/c633d358-dbb9-49d0-a186-0fbe3bc85f6a)

Pertanyaan dan Tugas
1. Selesaikan semua langkah praktikum di atas.
2. Modifikasi tampilan data artikel dan pagination sesuai kebutuhan desain.

![Screenshot 2025-06-19 214251](https://github.com/user-attachments/assets/33b43aed-d99a-45ac-9182-de22a769b9fa)

3. Tambahkan indikator loading saat data sedang diambil dari server.

![image](https://github.com/user-attachments/assets/f6f021bd-9431-469d-8d8c-4ad9e7cb3637)

4. Implementasikan fitur sorting (mengurutkan artikel berdasarkan judul, dll.) dengan AJAX.

![image](https://github.com/user-attachments/assets/4730d1ed-1ef7-48d0-8a07-d5e40cc52b55)


Hasilnya :

![Screenshot 2025-07-07 140039](https://github.com/user-attachments/assets/beafc20b-c4a2-41ea-b470-d4bb743bf268)

67. Persiapan
Periapan awal adalah mengunduh aplikasi REST Client, ada banyak aplikasi yang dapat digunakan untuk
keperluan tersebut. Salah satunya adalah Postman. Postman – Merupakan aplikasi yang berfungsi
sebagai REST Client, digunakan untuk testing REST API. Unduh apliasi Postman dari tautan berikut:
https://www.postman.com/downloads/

68. Membuat Model.
Pada modul sebelumnya sudah dibuat ArtikelModel, pada modul ini kita akan memanfaatkan model
tersebut agar dapat diakses melalui API.

69. Membuat REST Controller
Pada tahap ini, kita akan membuat file REST Controller yang berisi fungsi untuk menampilkan,
menambah, mengubah dan menghapus data. Masuklah ke direktori app\Controllers dan buatlah file
baru bernama Post.php. Kemudian, salin kode di bawah ini ke dalam file tersebut:

![image](https://github.com/user-attachments/assets/4329ef04-69de-44b5-94ab-289cfcc4e9d2)

![image](https://github.com/user-attachments/assets/852374bc-0a2b-42af-ad3c-2b75b52cf8ac)

![image](https://github.com/user-attachments/assets/98558c92-8f10-4fad-9eab-1f6cd3d21183)

Kode diatas berisi 5 method, yaitu:
• index() – Berfungsi untuk menampilkan seluruh data pada database.
• create() – Berfungsi untuk menambahkan data baru ke database.
• show() – Berfungsi untuk menampilkan suatu data spesifik dari database.
• update() – Berfungsi untuk mengubah suatu data pada database.
• delete() – Berfungsi untuk menghapus data dari database.

70. Membuat Routing REST API
Untuk mengakses REST API CodeIgniter, kita perlu mendefinisikan route-nya terlebih dulu.
Caranya, masuklah ke direktori app/Config dan bukalah file Routes.php. Tambahkan kode
di bawah ini:

![image](https://github.com/user-attachments/assets/91f4967b-0e16-443e-a7d5-9f94048e8759)

Untuk mengecek route nya jalankan perintah berikut:

![image](https://github.com/user-attachments/assets/91ef61e3-3f3b-494e-b024-ec395049db8a)

Selanjutnya akan muncul daftar route yang telah dibuat.

![image](https://github.com/user-attachments/assets/dc130d5f-7898-4e0e-bbd4-e271e430c72e)

Seperti yang terlihat, satu baris kode routes yang di tambahkan akan menghasilkan banyak
Endpoint.
Selanjutnya melakukan uji coba terhadap REST API CodeIgniter.

71. Testing REST API CodeIgniter
Buka aplikasi postman dan pilih create new → HTTP Request

![image](https://github.com/user-attachments/assets/890a0541-a634-4ff5-8dbd-685eca172ffc)

72. Menampilkan Semua Data
Pilih method GET dan masukkan URL berikut:
http://localhost:8080/post
Lalu, klik Send. Jika hasil test menampilkan semua data artikel dari database, maka pengujian
berhasil.

![image](https://github.com/user-attachments/assets/f64d2583-357d-4ccf-9827-49f82399ed25)

73. Menampilkan Data Spesifik
Masih menggunakan method GET, hanya perlu menambahkan ID artikel di belakang URL
seperti ini:
http://localhost:8080/post/2
Selanjutnya, klik Send. Request tersebut akan menampilkan data artikel yang memiliki ID
nomor 2 di database.

![image](https://github.com/user-attachments/assets/25530ede-6dc5-46c9-907c-cdb07561b4d0)

74. Mengubah Data
Untuk mengubah data, silakan ganti method menjadi PUT. Kemudian, masukkan URL artikel
yang ingin diubah. Misalnya, ingin mengubah data artikel dengan ID nomor 2, maka masukkan
URL berikut:
http://localhost:8080/post/2
Selanjutnya, pilih tab Body. Kemudian, pilih x-www-form-uriencoded. Masukkan nama
atribut tabel pada kolom KEY dan nilai data yang baru pada kolom VALUE. Kalau sudah,
klik Send.

![image](https://github.com/user-attachments/assets/483f730c-5453-4b60-84d6-c2d124b96d47)

75. Menambahkan Data
Anda perlu menggunakan method POST untuk menambahkan data baru ke database.
Kemudian, masukkan URL berikut:
http://localhost:8080/post
Pilih tab Body, lalu pilih x-www-form-uriencoded. Masukkan atribut tabel pada kolom KEY
dan nilai data baru di kolom VALUE. Jangan lupa, klik Send.

![image](https://github.com/user-attachments/assets/99d40810-b938-4228-b0cd-ee101d37875c)

76. Menghapus Data
Pilih method DELETE untuk menghapus data. Lalu, masukkan URL spesifik data mana yang
ingin di hapus. Misalnya, ingin menghapus data nomor 3, maka URL-nya seperti ini:
http://localhost:8080/post/3
Langsung saja klik Send, maka akan mendapatkan pesan bahwa data telah berhasil dihapus dari
database.

![image](https://github.com/user-attachments/assets/dbb337cf-e57e-4b50-8d96-abb937c99945)

Praktikum 11

77. Persiapan
Untuk memulai penggunaan framework Vuejs, dapat dialkukan dengan menggunakan npm,
atau bisa juga dengan cara manual. Untuk praktikum kali ini kita akan gunakan cara manual.
Yang diperlukan adalah library Vuejs, Axios untuk melakukan call API REST. Menggunakan
CDN.
- Library VueJS

![image](https://github.com/user-attachments/assets/4bb158b6-7741-43fc-b597-2eb81a0e2f32)

- Library Axios

![image](https://github.com/user-attachments/assets/996dac72-6b46-469f-ae5d-76c23862fc02)

78. Struktur Direktory
Buat Project baru dengan struktur file dan directory seperti berikut:
│ index.html
└───assets
      ├───css
      │    │ style.css
      └───js
          │app.js

79. Menampilkan data
File index.html

![image](https://github.com/user-attachments/assets/e2e68dd1-b2e8-4d42-8e50-ec4a522f1f64)

![image](https://github.com/user-attachments/assets/df5f2ff6-2dd2-415c-96ff-e7fc95522e6a)

![image](https://github.com/user-attachments/assets/ca2cff42-9ab0-4a76-9166-3367009eacdd)

File apps.js

![image](https://github.com/user-attachments/assets/490e194a-53f4-44a9-9814-54a822a59270)

![image](https://github.com/user-attachments/assets/2f85c334-3e2b-4ca2-a975-45527d3a7dce)

![image](https://github.com/user-attachments/assets/59417eaf-dc19-4c74-b2d2-a68cb619ffcc)

Hasil Outputnya

![image](https://github.com/user-attachments/assets/f9d71dab-31b5-41e1-b60c-7eea4b69a449)

80. Form Tambah dan Ubah Data
Pada file index,html sispkan kode berikut sebelum table data.

![image](https://github.com/user-attachments/assets/71ba07af-4632-4d40-b742-99166662b702)

File app.js lengkapi kodenya.

![image](https://github.com/user-attachments/assets/6766d562-16ed-4a99-8958-ec57f7becc38)

![image](https://github.com/user-attachments/assets/dc673981-15df-45b3-bc3c-bea926c8f4ad)

![image](https://github.com/user-attachments/assets/1c650a3e-c6cd-4deb-9d7a-2f383ddf88ce)

File style.css

![image](https://github.com/user-attachments/assets/33930d9c-8efc-4ce5-938a-d008cfd4c788)

![image](https://github.com/user-attachments/assets/42bc24a8-34f7-4c0f-99a3-d1bbbb696164)

![image](https://github.com/user-attachments/assets/f89daa38-d17c-4efe-b844-f22f48e7efcc)

Hasil Outputnya

![image](https://github.com/user-attachments/assets/47ebcb65-6042-43c7-9a06-fd810cc202c3)
