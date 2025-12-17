# Laporan Praktikum Minggu 1 (sesuaikan minggu ke berapa?)
Topik: inheritance

## Identitas
- Nama  : INAYAH FIJANATIN
- NIM   : 240202908
- Kelas : 3IKKA

---

## Tujuan
(Tuliskan tujuan praktikum minggu ini.  
Contoh: Tujuan dari praktikum ini adalah untuk memahami dan menerapkan konsep inheritance (pewarisan class) dalam pemrograman berorientasi objek menggunakan bahasa Java.
mahasiswa diharapkan mampu:
1. Memahami hubungan antara superclass dan subclass dalam OOP.
2. Menggunakan keyword extends untuk membuat class turunan dari sebuah class induk.
3. Menggunakan keyword super untuk memanggil konstruktor dan atribut dari superclass.
4. Menghindari duplikasi kode dengan memanfaatkan pewarisan class.
5. Membangun struktur program yang lebih terorganisir dan mudah dikembangkan, khususnya pada sistem POS pertanian.
6. Mendemonstrasikan hierarki class dengan membuat beberapa jenis produk (Benih, Pupuk, dan AlatPertanian) yang berasal dari satu class induk (Produk).
---

## Dasar Teori
(Tuliskan ringkasan teori singkat (3–5 poin) yang mendasari praktikum.  
Contoh:  
1. Pemrograman Berorientasi Objek (Object Oriented Programming / OOP)
- Paradigma pemrograman yang memodelkan program dalam bentuk objek.
- Objek terdiri dari atribut (data) dan method (perilaku).
2. Class dan Object
- Class adalah cetak biru (blueprint) untuk membuat objek.
- Object adalah hasil instansiasi dari sebuah class.
3. Inheritance (Pewarisan Class)
- Mekanisme OOP yang memungkinkan suatu class mewarisi atribut dan method dari class lain.
4. Superclass
- Class induk yang berisi atribut dan method umum.
5. Subclass
- Class turunan yang mewarisi superclass.
6. Keyword extends
Digunakan untuk menyatakan bahwa suatu class merupakan turunan dari class lain.
Contoh: class Benih extends Produk.
7. Keyword super
Digunakan untuk memanggil konstruktor atau method milik superclass.
Memastikan atribut superclass terinisialisasi dengan benar.
8. Hierarki Class
- Struktur hubungan antara superclass dan subclass.
- Membantu pengelompokan objek berdasarkan kesamaan dan perbedaan sifat.
9. Manfaat Inheritance
- Menghindari penulisan kode yang berulang.
- Mempermudah pengembangan dan pemeliharaan program.
- Membuat struktur program lebih rapi dan terorganisir.
- Penerapan pada Sistem POS Pertanian
- Produk menyimpan atribut umum (kode, nama, harga, stok).
- Subclass menambahkan atribut khusus sesuai jenis produk.

---

## Langkah Praktikum
1. Persiapan dan Setup Lingkungan
- Menyiapkan perangkat lunak Java Development Kit (JDK).
- Menggunakan Visual Studio Code sebagai text editor.
- Membuka folder proyek praktikum week3-inheritance.
- Memastikan struktur folder dan package sudah sesuai dengan ketentuan praktikum.
2. Membuat Superclass Produk
- Membuat file Produk.java.
- Menentukan atribut umum produk, yaitu kode, nama, harga, dan stok.
- Membuat konstruktor untuk inisialisasi atribut.
- Menambahkan method getter untuk mengakses data produk.
3. Membuat Subclass Benih
- Membuat file Benih.java.
- Menjadikan class Benih sebagai turunan dari Produk menggunakan keyword extends.
- Menambahkan atribut khusus varietas.
- Menggunakan keyword super pada konstruktor untuk memanggil konstruktor Produk.
4. Membuat Subclass Pupuk
- Membuat file Pupuk.java.
- Mewarisi class Produk.
- Menambahkan atribut khusus jenis.
- Menggunakan super untuk inisialisasi atribut superclass.
5. Membuat Subclass AlatPertanian
- Membuat file AlatPertanian.java.
- Mewarisi class Produk.
- Menambahkan atribut khusus material.
- Menggunakan keyword super pada konstruktor.
6. Membuat Class MainInheritance
- Membuat file MainInheritance.java.
- Melakukan instansiasi objek Benih, Pupuk, dan AlatPertanian.
- Menampilkan data dari masing-masing objek untuk membuktikan inheritance berjalan dengan baik.
7. Menambahkan Class CreditBy
- Membuat file CreditBy.java.
- Menampilkan identitas mahasiswa (NIM dan Nama) pada akhir program.
8. Menjalankan Program
- Melakukan kompilasi dan eksekusi program melalui terminal VS Code.
- Memastikan program berjalan tanpa error.
- Mengamati output yang menampilkan data dari setiap subclass.
9. Dokumentasi Hasil
- Mengambil screenshot hasil eksekusi program.
- Menyimpan screenshot ke dalam folder screenshots.
10. Commit dan Push ke Repository
- Melakukan commit seluruh perubahan ke repository Git.
- Menggunakan commit message:

---

## Kode Program
###
public class Benih extends Produk {
    private String varietas;

    public Benih(String kode, String nama, double harga, int stok, String varietas) {
        super(kode, nama, harga, stok);
        this.varietas = varietas;
    }

    public String getVarietas() {
        return varietas;
    }
}

###
public class Pupuk extends Produk {
    private String jenis;

    public Pupuk(String kode, String nama, double harga, int stok, String jenis) {
        super(kode, nama, harga, stok);
        this.jenis = jenis;
    }

    public String getJenis() {
        return jenis;
    }
}



## Hasil Eksekusi
(Sertakan screenshot hasil eksekusi program.  
![Screenshot hasil](screenshots/hasil.png)
)
---

## Analisis
(
- Jelaskan bagaimana kode berjalan.  
- Apa perbedaan pendekatan minggu ini dibanding minggu sebelumnya.  
- Kendala yang dihadapi dan cara mengatasinya.  
)
---

## Kesimpulan
(Tuliskan kesimpulan dari praktikum minggu ini.  
Contoh: *Dengan menggunakan class dan object, program menjadi lebih terstruktur dan mudah dikembangkan.*)

---

## Quiz
(1. [Tuliskan kembali pertanyaan 1 dari panduan]  
   **Jawaban:** …  

2. [Tuliskan kembali pertanyaan 2 dari panduan]  
   **Jawaban:** …  

3. [Tuliskan kembali pertanyaan 3 dari panduan]  
   **Jawaban:** …  )
