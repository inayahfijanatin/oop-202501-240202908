# Laporan Praktikum Minggu 10
Topik: Design Pattern (Singleton, MVC) dan Unit Testing menggunakan JUnit

## Identitas
- Nama  : Inayah Fijanatin
- NIM   : 240202908
- Kelas : 3IKKA

---

## Tujuan
Tujuan dari praktikum minggu ke-10 adalah agar mahasiswa:
1. Memahami konsep dasar design pattern dalam pengembangan perangkat lunak.
2. Mampu mengimplementasikan Singleton Pattern dengan benar.
3. Menerapkan arsitektur Model–View–Controller (MVC) pada aplikasi sederhana.
4. Membuat dan menjalankan unit testing menggunakan JUnit.
5. Menganalisis manfaat design pattern dan unit testing terhadap kualitas perangkat lunak.

## Dasar Teori
1. Design Pattern adalah solusi desain umum yang dapat digunakan kembali untuk menyelesaikan masalah tertentu dalam pengembangan software.
2. Singleton Pattern memastikan sebuah class hanya memiliki satu instance selama aplikasi berjalan.
3. MVC (Model–View–Controller) memisahkan logika bisnis, tampilan, dan pengontrol aplikasi.
4. Unit Testing digunakan untuk menguji unit terkecil dari program agar berjalan sesuai harapan.
5. JUnit merupakan framework testing pada Java yang menyediakan anotasi dan assertion.
---

## Langkah Praktikum
1. Membuat folder week10-pattern-testing.
2. Membuat struktur package model, view, controller, dan config.
3. Mengimplementasikan Singleton Pattern pada class DatabaseConnection.
4. Menerapkan pola MVC untuk fitur Product.
5. Membuat class AppMVC sebagai main program.
6. Membuat unit test menggunakan JUnit 5 pada class ProductTest.
7. Menjalankan unit test hingga berhasil tanpa error.
8. Mendokumentasikan hasil eksekusi dan unit test.
---

## Kode Program

**Singleton – DatabaseConnection
**

package com.upb.agripos.config;

public class DatabaseConnection {
    private static DatabaseConnection instance;

    private DatabaseConnection() {}

    public static DatabaseConnection getInstance() {
        if (instance == null) {
            instance = new DatabaseConnection();
        }
        return instance;
    }
}

**Model – Product**

package com.upb.agripos.model;

public class Product {
    private String code;
    private String name;
    private double price;
    private int stock;

    public Product(String code, String name, double price, int stock) {
        this.code = code;
        this.name = name;
        this.price = price;
        this.stock = stock;
    }

    public String getCode() { return code; }
    public String getName() { return name; }
}


**View – ConsoleView**
package com.upb.agripos.view;

public class ConsoleView {
    public void showMessage(String message) {
        System.out.println(message);
    }
}

**Controller – ProductController**

package com.upb.agripos.controller;

import com.upb.agripos.model.Product;
import com.upb.agripos.view.ConsoleView;

public class ProductController {
    private Product model;
    private ConsoleView view;

    public ProductController(Product model, ConsoleView view) {
        this.model = model;
        this.view = view;
    }

    public void showProduct() {
        view.showMessage("Produk: " + model.getCode() + " - " + model.getName());
    }
}

**Main Program – AppMVC**
package com.upb.agripos;

import com.upb.agripos.model.Product;
import com.upb.agripos.view.ConsoleView;
import com.upb.agripos.controller.ProductController;

public class AppMVC {
    public static void main(String[] args) {
        System.out.println("Hello, I am Inayah Fijanatin-240202908 (Week10)");

        Product product = new Product("P01", "Pupuk Organik", 15000, 10);
        ConsoleView view = new ConsoleView();
        ProductController controller = new ProductController(product, view);

        controller.showProduct();
    }
}

**Unit Test – ProductTest**
package com.upb.agripos;

import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;
import com.upb.agripos.model.Product;

public class ProductTest {

    @Test
    public void testProductName() {
        Product p = new Product("P01", "Benih Jagung", 20000, 5);
        assertEquals("Benih Jagung", p.getName());
    }
}


## Hasil Eksekusi
(Hasil di SS)
---

## Analisis
1. Singleton memastikan hanya satu instance DatabaseConnection yang digunakan.
2. MVC membuat struktur program lebih rapi dan mudah dikembangkan.
3. Unit test membantu memastikan method berjalan sesuai harapan.
4. Kendala utama adalah perbedaan constructor Product, yang diselesaikan dengan menyesuaikan parameter pada AppMVC dan ProductTest.
5. Setelah dependensi JUnit terpasang, unit test dapat dijalankan dengan sukses.
---

## Kesimpulan
Penerapan design pattern Singleton dan MVC membuat aplikasi lebih terstruktur dan terkontrol. Unit testing menggunakan JUnit membantu mendeteksi kesalahan lebih awal sehingga meningkatkan kualitas dan keandalan perangkat lunak.

## Quiz
1. Mengapa constructor pada Singleton harus private?
Jawaban: Agar object tidak dapat dibuat langsung dari luar class.

2. Apa manfaat MVC?
Jawaban: Memisahkan logika bisnis, tampilan, dan pengontrol sehingga kode lebih rapi dan mudah dirawat.

3. Apa peran unit testing?
Jawaban: Memastikan fungsi berjalan sesuai harapan dan mencegah bug.

4. Apa risiko Singleton yang salah implementasi?
Jawaban: Dapat menyebabkan lebih dari satu instance dan konflik data.
3. [Tuliskan kembali pertanyaan 3 dari panduan]  
   **Jawaban:** …  )
