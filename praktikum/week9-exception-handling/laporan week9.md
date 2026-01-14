# Laporan Praktikum Minggu 9 
Topik: 

## Identitas
- Nama  : Inayah Fijanatin
- NIM   : 240202908
- Kelas : 3IKKA

---

## Tujuan
(Tuliskan tujuan praktikum minggu ini.  
1. Memahami perbedaan antara error dan exception dalam Java.
2. Mengimplementasikan try–catch–finally untuk menangani kesalahan program.
3. Membuat dan menggunakan custom exception sesuai kebutuhan program.
4. Mengintegrasikan exception handling pada keranjang belanja untuk memvalidasi quantity dan stok produk.
5. Mempelajari konsep design pattern sederhana (opsional).

---

## Dasar Teori
(Tuliskan ringkasan teori singkat (3–5 poin) yang mendasari praktikum.  
Dasar Teori
1. Error vs Exception
  - Error → kondisi fatal yang tidak bisa ditangani (contoh: OutOfMemoryError).
  - Exception → kondisi tidak normal yang bisa ditangani oleh program.
2. Try–Catch–Finally
  - Try → blok kode yang berpotensi menimbulkan exception.
  - Catch → blok untuk menangkap exception dan memberikan penanganan.
  - Finally → blok kode yang selalu dijalankan, baik terjadi exception atau tidak.
3. Custom Exception
  - Exception khusus yang dibuat sendiri agar lebih jelas dan sesuai kebutuhan bisnis.
  - Contoh: InvalidQuantityException, ProductNotFoundException, InsufficientStockException.
4. ShoppingCart dengan Validasi
  - Menggunakan Map<Product, Integer> untuk menyimpan produk dan quantity.
  - Menangani penambahan produk, penghapusan, dan checkout dengan validasi stok.
    
## Langkah Praktikum
1. Persiapan Project
   - Buat folder project: praktikum/week9-exception-handling
   - Buat package: com.upb.agripos
   - Siapkan IDE (IntelliJ IDEA/VS Code).
2. Membuat Custom Exception
  - InvalidQuantityException.java
  - ProductNotFoundException.java
  - InsufficientStockException.java
3. Membuat Product.java
  - Tambahkan atribut stock
  - Tambahkan method reduceStock(int qty)
4. Membuat ShoppingCart.java
  - Gunakan Map<Product, Integer>
  - Implementasikan metode: addProduct, removeProduct, checkout, printCart
  - Tambahkan exception handling pada setiap metode sesuai kasus
5. Membuat MainExceptionDemo.java
  - Tambahkan produk ke keranjang, hapus produk, checkout
  - Gunakan try-catch untuk menangkap exception
  - Jalankan program untuk memastikan exception muncul sesuai skenario
6. Commit & Push

---

## Kode Program

MainExceptionDemo.java

package com.upb.agripos;

public class MainExceptionDemo {
    public static void main(String[] args) {
        System.out.println("Hello, I am [Inayah Fijanatin]-[240202908] (Week9)");

        Product p1 = new Product("P01", "Pupuk Organik", 25000, 3);
        Product p2 = new Product("P02", "Beras", 50000, 10);

        ShoppingCart cart = new ShoppingCart();

        // Tambah produk
        try {
            cart.addProduct(p1, -1); // Quantity invalid
        } catch (InvalidQuantityException e) {
            System.out.println("Kesalahan: " + e.getMessage());
        }

        try {
            cart.removeProduct(p1); // Produk belum ada
        } catch (ProductNotFoundException e) {
            System.out.println("Kesalahan: " + e.getMessage());
        }

        try {
            cart.addProduct(p1, 5); // Stock tidak cukup
            cart.checkout();
        } catch (Exception e) {
            System.out.println("Kesalahan: " + e.getMessage());
        }

        try {
            cart.addProduct(p1, 2); // Stock cukup
            cart.checkout();
            cart.printCart();
        } catch (Exception e) {
            System.out.println("Kesalahan: " + e.getMessage());
        }
    }
}

## Hasil Eksekusi
ada di SS (JPG)
---

## Analisis
1. Program berjalan dengan exception handling, sehingga tidak crash walau terjadi error.
2. Custom exception memberikan pesan yang jelas sesuai kasus: quantity negatif, produk tidak ada, stok kurang.
3. Pendekatan minggu ini berbeda dengan minggu sebelumnya (Bab 7) karena sebelumnya keranjang tanpa validasi quantity dan stok.
4. Kendala: memahami cara menggunakan try-catch dengan metode yang melempar exception. Solusi: membaca dokumentasi Java tentang throws dan try-catch.

---

## Kesimpulan
- Dengan menggunakan exception handling, program menjadi lebih aman dan mudah dipelihara.
- Custom exception membantu memberi pesan error spesifik, sesuai kondisi bisnis (misal stok kurang).
- Praktikum ini meningkatkan pemahaman tentang error handling dan validasi di program berbasis OOP.

---

## Quiz
1. Jelaskan perbedaan error dan exception.
Jawaban:
Error adalah kondisi fatal di Java yang tidak bisa ditangani, seperti OutOfMemoryError.
Exception adalah kondisi tidak normal yang bisa ditangani dengan try-catch.

2. Apa fungsi finally dalam blok try–catch–finally?
Jawaban:
Blok finally selalu dijalankan, baik terjadi exception maupun tidak, biasanya digunakan untuk cleanup seperti menutup file atau koneksi.

3. Mengapa custom exception diperlukan?
Jawaban:
Agar program memberikan pesan kesalahan yang spesifik sesuai kasus bisnis, memudahkan debugging dan validasi logika.

4. Berikan contoh kasus bisnis dalam POS yang membutuhkan custom exception.
Jawaban:
Misalnya customer mencoba membeli lebih banyak barang daripada stok tersedia → lempar InsufficientStockException.
Atau customer memasukkan quantity negatif → lempar InvalidQuantityException.

3. [Tuliskan kembali pertanyaan 3 dari panduan]  
   **Jawaban:** …  )
