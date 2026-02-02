# Laporan Praktikum Minggu 14
Topik: Integrasi Individu Lanjutan (OOP + Database + Gui)

## Identitas
- Nama  : Inayah Fijanatin
- NIM   : 240202908
- Kelas : 3IKKA

---

## Tujuan
Mahasiswa mampu mengintegrasikan konsep Object Oriented Programming (OOP), Collections, Exception Handling, Design Pattern, Database (JDBC), dan GUI JavaFX ke dalam satu aplikasi utuh berupa aplikasi kasir sederhana (Agri-POS).
---

## Dasar Teori
1. OOP (Object Oriented Programming) digunakan untuk memodelkan aplikasi melalui class, object, enkapsulasi, dan pemisahan tanggung jawab.
2. Collections Framework digunakan untuk mengelola data dinamis seperti keranjang belanja menggunakan List dan Map.
3. (Data Access Object) berfungsi sebagai penghubung antara aplikasi dan database menggunakan JDBC.
4. MVC + Service Layer diterapkan untuk memisahkan View, Controller, Service, dan DAO sesuai prinsip SOLID dan DIP.
5. JavaFX digunakan untuk membangun antarmuka grafis yang interaktif dan terhubung dengan backend.

---

## Langkah Praktikum
1. Mengintegrasikan class dari Bab 1–13 ke dalam satu project Agri-POS.
2. Menghubungkan aplikasi JavaFX dengan database PostgreSQL menggunakan JDBC dan DAO.
3. Mengimplementasikan TableView untuk menampilkan data produk dari database.
4. Mengimplementasikan keranjang belanja menggunakan Collections.
5. Menambahkan validasi dan error flow menggunakan exception.
6. Membuat unit test JUnit untuk menguji logika CartService.
7. Menjalankan aplikasi dan melakukan pengujian fitur CRUD produk dan keranjang.

---

## Kode Program
kode utama pada controller untuk menambah produk dan keranjang:

public void tambahProduk(Product product) throws Exception {
    productService.insert(product);
}

public void addToCart(Product product, int qty) {
    cartService.addToCart(product, qty);
}

## Hasil Eksekusi
di ss

## Analisis
- Aplikasi berjalan dengan alur View → Controller → Service → DAO → Database.
- Berbeda dengan minggu sebelumnya, pada minggu ini seluruh konsep digabungkan menjadi satu aplikasi utuh.
- Kendala utama adalah error duplicate class dan method tidak sinkron antara service dan unit test.

Kendala diatasi dengan pemisahan file sesuai aturan Java dan penyamaan method antara implementasi dan test.
---

## Kesimpulan
Dengan mengintegrasikan OOP, Collections, Exception Handling, DAO, dan JavaFX, aplikasi Agri-POS dapat berjalan secara end-to-end. Penerapan arsitektur berlapis dan prinsip SOLID membuat kode lebih rapi, terstruktur, dan mudah dikembangkan.

## Quiz
1. Jelaskan fungsi Service Layer dalam aplikasi ini
Jawaban:
Service Layer berfungsi sebagai penghubung antara Controller dan DAO serta tempat logika bisnis, sehingga View tidak langsung berkomunikasi dengan database.

2. Mengapa Collections digunakan pada keranjang belanja?
Jawaban:
Karena Collections memungkinkan penyimpanan data secara dinamis dan efisien untuk menambah, menghapus, serta menghitung total item.

3. Apa keuntungan penggunaan DAO pada aplikasi Agri-POS?
Jawaban:
DAO memisahkan logika database dari aplikasi utama sehingga kode lebih terstruktur, mudah diuji, dan mudah dikembangkan.

3. [Tuliskan kembali pertanyaan 3 dari panduan]  
   **Jawaban:** …  )
