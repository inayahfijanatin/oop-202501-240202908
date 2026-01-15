# Laporan Praktikum Minggu 11
Topik: Data Access Object (DAO) dan CRUD Database dengan JDBC

## Identitas
- Nama  : Inayah Fijanatin
- NIM   : 240202908
- Kelas : 3IKKA

---

## Tujuan
Tujuan dari praktikum minggu ke-11 adalah agar mahasiswa mampu memahami dan mengimplementasikan pola desain Data Access Object (DAO) menggunakan JDBC untuk melakukan operasi CRUD (Create, Read, Update, Delete) pada basis data PostgreSQL secara terstruktur dan sesuai prinsip pemrograman berorientasi objek.

-----

## Dasar Teori
1. Data Access Object (DAO) adalah pola desain yang memisahkan logika akses data dari logika bisnis aplikasi.
2. JDBC (Java Database Connectivity) digunakan untuk menghubungkan aplikasi Java dengan database relasional.
3. Operasi CRUD terdiri dari Create, Read, Update, dan Delete.
4. PreparedStatement digunakan untuk meningkatkan keamanan dan efisiensi query SQL.
5. Pemisahan antara model, DAO, dan main program membuat aplikasi lebih mudah dikembangkan dan dipelihara.
   
---

## Langkah Praktikum
1. Menginstal dan menjalankan PostgreSQL serta pgAdmin.
2. Membuat database agripos dan tabel products.
3. Membuat class model Product.
4. Membuat interface ProductDAO.
5. Mengimplementasikan DAO menggunakan JDBC pada ProductDAOImpl.
6. Menambahkan PostgreSQL JDBC Driver ke project.
7. Membuat class MainDAOTest untuk menguji operasi CRUD.
8. Menjalankan program dan memastikan seluruh operasi CRUD berjalan dengan baik.

---

## Kode Program
Contoh Kode di MainDAOTest.java

ProductDAO dao = new ProductDAOImpl(conn);
dao.insert(new Product("P99", "Tes DAO", 10000, 5));

Product p = dao.findByCode("P99");
System.out.println(p.getName());

dao.update(new Product("P99", "Tes DAO Update", 12000, 10));

dao.delete("P99");

## Hasil Eksekusi
di SS
---

## Analisis
1. Program berjalan dengan cara membuat koneksi JDBC ke PostgreSQL, kemudian DAO digunakan untuk melakukan operasi CRUD tanpa menuliskan SQL langsung di main().
2. Perbedaan dengan minggu sebelumnya adalah pada minggu ini aplikasi sudah terhubung dengan database nyata dan menggunakan DAO untuk akses data.
3. Kendala yang dihadapi adalah error koneksi database karena driver PostgreSQL belum ditambahkan ke classpath. Masalah ini diatasi dengan menambahkan file postgresql-42.7.8.jar ke library project.
   
---

## Kesimpulan
Dengan menerapkan pola desain DAO dan JDBC, aplikasi menjadi lebih terstruktur, aman, dan mudah dikembangkan. Operasi CRUD dapat dilakukan dengan baik tanpa mencampur logika database dengan logika utama aplikasi.

---

## Quiz
1. Mengapa DAO diperlukan dalam aplikasi OOP?
Jawaban: DAO memisahkan logika akses data dari logika bisnis sehingga kode lebih terstruktur dan mudah dipelihara.

2. Apa fungsi PreparedStatement dalam JDBC?
Jawaban: Untuk menjalankan query SQL dengan aman, mencegah SQL Injection, dan meningkatkan efisiensi eksekusi.

3. Sebutkan operasi CRUD dan fungsinya!
Jawaban:
  - Create: menambah data
  - Read: membaca data
  - Update: memperbarui data
  - Delete: menghapus data
