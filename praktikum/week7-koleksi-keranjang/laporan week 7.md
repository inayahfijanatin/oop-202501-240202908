# Laporan Praktikum Minggu 7
Topik: Collections dan Implementasi Keranjang Belanja

## Identitas
- Nama  : Inayah Fijanatin
- NIM   : 240202908
- Kelas : 3IKKA

---

## Tujuan
(Tuliskan tujuan praktikum minggu ini.  
Mahasiswa mampu:
1. Menjelaskan konsep collection dalam Java (List, Map, Set).
2. Menggunakan ArrayList dan Map untuk menyimpan dan mengelola objek.
3. Mengimplementasikan keranjang belanja sederhana dengan operasi tambah, hapus, dan hitung total.
4. Menganalisis efisiensi penggunaan collection dalam konteks sistem Agri-POS.
   
## Dasar Teori
1. List: Struktur data terurut yang dapat menyimpan elemen duplikat; contoh implementasi: ArrayList.
2. Map: Struktur data pasangan key–value, cocok untuk menyimpan objek dengan jumlah/quantity; contoh: HashMap.
3. Set: Struktur data yang unik, tidak memperbolehkan duplikasi; contoh: HashSet.
4. ArrayList vs Map: ArrayList mudah digunakan untuk daftar sederhana, Map cocok saat butuh jumlah per item.
5. Keranjang Belanja: Mengelola produk yang dipilih oleh pelanggan dengan menambahkan, menghapus, dan menghitung total harga.
   
---

## Langkah Praktikum
1. Membuat kelas Product dengan atribut code, name, dan price.
2. Membuat kelas ShoppingCart menggunakan ArrayList untuk menampung produk.
3. Menambahkan method untuk addProduct, removeProduct, getTotal, dan printCart.
4. Membuat MainCart untuk menjalankan keranjang belanja dan mencetak output.
5. Membuat implementasi alternatif menggunakan Map<Product, Integer> agar dapat menyimpan jumlah tiap produk.
6. Menjalankan program, memeriksa output, dan menyimpan screenshot hasil eksekusi (screenshots/hasil.png).
7. Commit & push ke repository:
   
---

## Kode Program
(Tuliskan kode utama yang dibuat, contoh:  

**Product.Java**
package com.upb.agripos;

public class Product {
    private final String code;
    private final String name;
    private final double price;

    public Product(String code, String name, double price) {
        this.code = code;
        this.name = name;
        this.price = price;
    }

    public String getCode() { return code; }
    public String getName() { return name; }
    public double getPrice() { return price; }
}

**ShoppingCart.Java**
package com.upb.agripos;

import java.util.ArrayList;

public class ShoppingCart {
    private final ArrayList<Product> items = new ArrayList<>();

    public void addProduct(Product p) { items.add(p); }
    public void removeProduct(Product p) { items.remove(p); }

    public double getTotal() {
        double sum = 0;
        for (Product p : items) sum += p.getPrice();
        return sum;
    }

    public void printCart() {
        System.out.println("Isi Keranjang:");
        for (Product p : items)
            System.out.println("- " + p.getCode() + " " + p.getName() + " = " + p.getPrice());
        System.out.println("Total: " + getTotal());
    }
}


**MainCart.Java**
package com.upb.agripos;

public class MainCart {
    public static void main(String[] args) {
        System.out.println("Hello, I am [Nama]-[NIM] (Week7)");

        Product p1 = new Product("P01", "Beras", 50000);
        Product p2 = new Product("P02", "Pupuk", 30000);

        ShoppingCart cart = new ShoppingCart();
        cart.addProduct(p1);
        cart.addProduct(p2);
        cart.printCart();

        cart.removeProduct(p1);
        cart.printCart();
    }
}


## Hasil Eksekusi
di SS
---

## Analisis
- Program berjalan dengan baik, menambahkan produk ke keranjang, menghitung total, dan menghapus produk sesuai perintah.
- Pendekatan minggu ini lebih kompleks dibanding minggu sebelumnya karena menggunakan collections untuk mengelola banyak objek dan quantity.
- Kendala: awalnya lupa import java.util.ArrayList dan typo pada nama kelas Product. Cara mengatasinya: menambahkan import dan memperbaiki nama file/class agar sesuai.
- 
## Kesimpulan
Dengan menggunakan class dan collections, keranjang belanja dapat dikelola secara dinamis, efisien, dan terstruktur. ArrayList cocok untuk daftar sederhana, sedangkan Map membantu jika ingin menyimpan jumlah tiap produk.
---

## Quiz
1. Jelaskan perbedaan mendasar antara List, Map, dan Set.
Jawaban:
  - List: terurut, boleh ada duplikasi. Contoh: ArrayList.
  - Map: pasangan key–value, akses cepat berdasarkan key. Contoh: HashMap.
  - Set: tidak boleh ada duplikasi, urutan tidak terjamin. Contoh: HashSet.

2. Mengapa ArrayList cocok digunakan untuk keranjang belanja sederhana?
Jawaban:
Karena ArrayList mudah digunakan untuk menyimpan dan mengakses elemen secara berurutan, serta operasi tambah/hapus cukup sederhana.

3. Bagaimana struktur Set mencegah duplikasi data?
Jawaban:
Set menggunakan prinsip hash atau aturan internal agar setiap elemen hanya muncul satu kali. Jika elemen yang sama ditambahkan, Set otomatis menolak duplikasi.

4. Kapan sebaiknya menggunakan Map dibandingkan List? Jelaskan dengan contoh.
Jawaban:
Map digunakan saat perlu menyimpan data dengan key unik dan value terkait, misal keranjang belanja yang menyimpan jumlah tiap produk. List hanya menyimpan daftar urut tanpa key.
