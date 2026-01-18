# Laporan Praktikum Minggu 12 
Topik: GUI Dasar

## Identitas
- Nama  : Inayah Fijanatin
- NIM   : 240202908
- Kelas : 3IKKA

---

## Tujuan
Tujuan dari praktikum minggu ke-12 ini adalah:
1. Mahasiswa memahami konsep event-driven programming pada aplikasi GUI.
2. Mahasiswa mampu membuat antarmuka grafis sederhana menggunakan JavaFX.
3. Mahasiswa mampu membuat form input data produk.
4. Mahasiswa mampu mengintegrasikan GUI dengan backend melalui ProductController dan ProductService.
5. Mahasiswa mampu menampilkan data produk hasil input pada tampilan GUI.
   
---

## Dasar Teori
1. GUI (Graphical User Interface) adalah antarmuka berbasis grafis yang memungkinkan pengguna berinteraksi dengan aplikasi melalui komponen visual seperti button, textfield, dan list.
2. JavaFX adalah framework Java yang digunakan untuk membangun aplikasi GUI modern berbasis event.
3. Event-driven programming adalah paradigma pemrograman di mana alur program ditentukan oleh event seperti klik tombol atau input pengguna.
4. MVC (Model View Controller) memisahkan logika aplikasi menjadi Model (data), View (tampilan), dan Controller (penghubung).
5. Service dan DAO digunakan untuk memisahkan logika bisnis dan akses data sehingga GUI tidak langsung berhubungan dengan database.

---

## Langkah Praktikum
1. Menyiapkan Java Development Kit (JDK) dan JavaFX SDK.
2. Membuat project JavaFX di NetBeans.
3. Menggunakan kembali kode backend Week 11 (Product, ProductDAO, ProductService).
4. Membuat class:
   - ProductController untuk menangani logika dari GUI.
   - ProductFormView untuk tampilan form input produk.
   - AppJavaFX sebagai entry point aplikasi JavaFX.
5. Menambahkan event handler pada tombol “Tambah Produk”.
6. Menghubungkan GUI dengan ProductService tanpa mengakses DAO secara langsung.
7. Menjalankan aplikasi dan melakukan pengujian input produk.
---

## Kode Program

AppJavaFX.java
public class AppJavaFX extends Application {
    @Override
    public void start(Stage stage) {
        ProductFormView view = new ProductFormView();
        Scene scene = new Scene(view.getView(), 500, 450);
        stage.setTitle("Agri-POS - Kelola Produk");
        stage.setScene(scene);
        stage.show();
    }
}

Event Handler pada GUI
btnAdd.setOnAction(event -> {
    Product p = new Product(
        txtCode.getText(),
        txtName.getText(),
        Double.parseDouble(txtPrice.getText()),
        Integer.parseInt(txtStock.getText())
    );
    controller.addProduct(p);
    listView.getItems().add(p.getCode() + " - " + p.getName());
});


## Hasil Eksekusi
di SS

## Analisis
- Program berjalan dengan pendekatan event-driven, di mana aksi pengguna (klik tombol) memicu proses penyimpanan data.
- Dibandingkan minggu sebelumnya (Week 11), praktikum ini tidak menggunakan console, melainkan antarmuka grafis.
- GUI tidak berinteraksi langsung dengan database, melainkan melalui Controller → Service → DAO, sesuai prinsip Dependency Inversion Principle (DIP).
- Kendala utama adalah konfigurasi JavaFX SDK, yang diatasi dengan menambahkan VM Options dan library JavaFX pada project.

## Kesimpulan
Dari praktikum ini dapat disimpulkan bahwa penggunaan JavaFX memungkinkan pembuatan aplikasi yang lebih interaktif dan user-friendly. Dengan menerapkan konsep MVC dan event-driven programming, aplikasi menjadi lebih terstruktur, mudah dikembangkan, dan sesuai dengan desain sistem yang telah dibuat pada Bab sebelumnya.

---

## Quiz
1. Apa yang dimaksud dengan event-driven programming?
Jawaban: Event-driven programming adalah paradigma pemrograman di mana alur program ditentukan oleh event seperti klik tombol atau input pengguna.

2. Mengapa GUI tidak boleh langsung mengakses DAO?
Jawaban: Agar tetap mengikuti prinsip MVC dan SOLID, sehingga tampilan tidak bergantung langsung pada akses database.

3. Class apa yang berfungsi sebagai penghubung antara GUI dan backend?
Jawaban: ProductController.
3. [Tuliskan kembali pertanyaan 3 dari panduan]  
   **Jawaban:** …  )
