# Laporan Praktikum Minggu 13
Topik: GUI Lanjutan

## Identitas
- Nama  : Inayah Fijanatin
- NIM   : 240202908
- Kelas : 3IKKA

---

## Tujuan
Mahasiswa memahami konsep GUI lanjutan dengan JavaFX TableView dan Lambda Expression, serta mampu mengintegrasikan GUI dengan DAO melalui service layer untuk membangun aplikasi Agri-POS yang interaktif.
---

## Dasar Teori
1. TableView JavaFX adalah komponen untuk menampilkan data dalam format tabel dengan kolom dan baris, mendukung pengurutan, filter, dan seleksi baris.
2. ObservableList adalah koleksi khusus JavaFX yang dapat diamati, memungkinkan UI otomatis terupdate ketika data berubah.
3. Lambda Expression adalah fitur Java 8+ untuk menyederhanakan penulisan kode, terutama untuk event handling dan functional interfaces.
4. PropertyValueFactory digunakan untuk memetakan property objek ke kolom TableView secara otomatis.
5. MVC Pattern diterapkan dengan memisahkan View (JavaFX), Controller (business logic), dan Model (data classes).

---

## Langkah Praktikum
1. Melanjutkan project JavaFX dari praktikum Minggu 12 tanpa membuat project baru.
2. Membuat dan memastikan class Product sebagai model memiliki getter yang sesuai untuk TableView.
3. Mengimplementasikan ProductDAO untuk mengambil dan menghapus data produk dari database PostgreSQL.
4. Membuat ProductService sebagai perantara antara controller dan DAO.
5. Mengimplementasikan ProductController untuk menangani logika pemanggilan service.
6. Membuat tampilan ProductTableView menggunakan JavaFX TableView.
7. Menambahkan tombol Tambah Produk dan Hapus Produk dengan event handler menggunakan lambda expression.
8. Menguji aplikasi dan memastikan data pada TableView sesuai dengan isi database.
9. Melakukan commit dengan pesan:
---

## Kode Program
ProductTableView

package com.upb.agripos.view;

import com.upb.agripos.controller.ProductController;
import com.upb.agripos.model.Product;

import javafx.collections.FXCollections;
import javafx.collections.ObservableList;
import javafx.geometry.Insets;
import javafx.scene.control.*;
import javafx.scene.control.cell.PropertyValueFactory;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.HBox;

public class ProductTableView extends BorderPane {

    private final TableView<Product> table = new TableView<>();
    private final ObservableList<Product> data = FXCollections.observableArrayList();
    private final ProductController controller;

    public ProductTableView(ProductController controller) {
        this.controller = controller;

        setPadding(new Insets(10));

        TableColumn<Product, String> colCode = new TableColumn<>("Kode");
        colCode.setCellValueFactory(new PropertyValueFactory<>("code"));

        TableColumn<Product, String> colName = new TableColumn<>("Nama");
        colName.setCellValueFactory(new PropertyValueFactory<>("name"));

        TableColumn<Product, Double> colPrice = new TableColumn<>("Harga");
        colPrice.setCellValueFactory(new PropertyValueFactory<>("price"));

        TableColumn<Product, Integer> colStock = new TableColumn<>("Stok");
        colStock.setCellValueFactory(new PropertyValueFactory<>("stock"));

        table.getColumns().addAll(colCode, colName, colPrice, colStock);
        table.setItems(data);
        table.setColumnResizePolicy(TableView.CONSTRAINED_RESIZE_POLICY);

        // Tombol
        Button btnAdd = new Button("Tambah Produk");
        Button btnDelete = new Button("Hapus Produk");

        // ✅ Lambda Expression
        btnDelete.setOnAction(e -> {
            Product selected = table.getSelectionModel().getSelectedItem();
            if (selected != null) {
                controller.deleteProduk(selected);
                loadData();
            } else {
                Alert alert = new Alert(Alert.AlertType.WARNING);
                alert.setTitle("Peringatan");
                alert.setHeaderText(null);
                alert.setContentText("Silakan pilih produk terlebih dahulu.");
                alert.showAndWait();
            }
        });

        HBox buttonBox = new HBox(10, btnAdd, btnDelete);
        buttonBox.setPadding(new Insets(10));

        setCenter(table);
        setBottom(buttonBox);

        loadData();
    }

    private void loadData() {
        data.clear();
        data.addAll(controller.loadProduk());
    }
}


---

## Hasil Eksekusi
di ss

## Analisis
- Program berjalan dengan memanfaatkan arsitektur MVC, di mana View hanya menangani tampilan, Controller mengelola alur logika, dan Service serta DAO menangani akses data.
- Perbedaan utama praktikum minggu ini dibanding minggu sebelumnya adalah penggunaan TableView sebagai pengganti tampilan data sederhana serta penerapan lambda expression untuk event handling.
- Kendala yang dihadapi adalah kesalahan pemetaan kolom TableView dengan properti model. Kendala ini diatasi dengan memastikan nama properti pada PropertyValueFactory sesuai dengan getter pada class model.
---

## Kesimpulan
Berdasarkan praktikum minggu ke-13, dapat disimpulkan bahwa penggunaan TableView dan lambda expression pada JavaFX membuat aplikasi menjadi lebih interaktif dan efisien. Integrasi GUI dengan DAO melalui service layer menjadikan struktur aplikasi lebih rapi, terpisah dengan baik, serta mudah dikembangkan untuk tahap selanjutnya.
---

## Quiz
1. Apa fungsi TableView dalam JavaFX?
Jawaban: TableView berfungsi untuk menampilkan data dalam bentuk tabel yang terdiri dari baris dan kolom serta mendukung seleksi dan pengolahan data.

2. Apa kegunaan Lambda Expression pada praktikum ini?
Jawaban: Lambda Expression digunakan untuk menyederhanakan penulisan event handler, sehingga kode menjadi lebih ringkas dan mudah dibaca.

3. Mengapa View tidak boleh langsung mengakses DAO?
Jawaban: Karena melanggar prinsip MVC dan SOLID. View seharusnya hanya menangani tampilan, sedangkan akses data dilakukan melalui controller dan service agar aplikasi lebih terstruktur.
