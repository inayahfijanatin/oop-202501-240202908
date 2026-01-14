# Laporan Praktikum Minggu 4 (sesuaikan minggu ke berapa?)
Topik: polymorphism

## Identitas
- Nama  : Inayah Fihanatin
- NIM   : 240202908
- Kelas : 3IKKA

---

## Tujuan
(Tuliskan tujuan praktikum minggu ini.  
Tujuan dari praktikum minggu ke-4 ini adalah agar mahasiswa memahami konsep polymorphism dalam Object Oriented Programming (OOP), membedakan antara method overloading dan method overriding, serta mampu mengimplementasikan dynamic binding dalam program Java pada studi kasus sistem Agri-POS.

---

## Dasar Teori
1. Polymorphism adalah konsep OOP yang memungkinkan satu method memiliki banyak bentuk perilaku.
2. Method overloading terjadi ketika method memiliki nama yang sama tetapi parameter berbeda.
3. Method overriding terjadi ketika subclass mengganti implementasi method dari superclass.
4. Dynamic binding menentukan method yang dipanggil berdasarkan objek sebenarnya saat runtime.

## Langkah Praktikum
1. Membuat dan menyiapkan struktur folder project week4-polymorphism.
2. Menambahkan method overloading tambahStok(int) dan tambahStok(double) pada class Produk.
3. Menambahkan method getInfo() pada superclass Produk.
4. Melakukan override method getInfo() pada subclass Benih, Pupuk, dan AlatPertanian.
5. Membuat array Produk[] yang berisi objek dari berbagai subclass.
6. Menjalankan program menggunakan MainPolymorphism.java.

## Kode Program

Produk[] daftarProduk = {
    new Benih("BNH-001", "Benih Padi IR64", 25000, 100, "IR64"),
    new Pupuk("PPK-101", "Pupuk Urea", 350000, 40, "Urea"),
    new AlatPertanian("ALT-501", "Cangkul Baja", 90000, 15, "Baja")
};

for (Produk p : daftarProduk) {
    System.out.println(p.getInfo());
}


## Hasil Eksekusi
(Sertakan screenshot hasil eksekusi program.  
**sudah ada di ss **

## Analisis
Pada praktikum ini, pemanggilan method getInfo() dilakukan melalui referensi superclass Produk, namun Java secara otomatis memanggil method milik subclass yang sesuai dengan objek sebenarnya. Hal ini menunjukkan penerapan dynamic binding. Perbedaan dengan minggu sebelumnya adalah pada minggu ke-3 hanya membahas inheritance, sedangkan minggu ke-4 memanfaatkan inheritance tersebut untuk menerapkan polymorphism. Kendala yang dihadapi adalah memahami perbedaan overloading dan overriding, namun dapat diatasi dengan melihat perbedaan parameter dan anotasi @Override.

## Kesimpulan
Berdasarkan praktikum yang telah dilakukan, dapat disimpulkan bahwa polymorphism memungkinkan satu method digunakan untuk berbagai objek dengan perilaku yang berbeda. Dengan konsep ini, program menjadi lebih fleksibel, terstruktur, dan mudah dikembangkan.

## Quiz
1. Apa perbedaan overloading dan overriding?
Jawaban: Overloading adalah method dengan nama yang sama tetapi parameter berbeda, sedangkan overriding adalah penggantian implementasi method superclass oleh subclass.

2. Bagaimana Java menentukan method mana yang dipanggil dalam dynamic binding?
Jawaban: Java menentukan method yang dipanggil berdasarkan tipe objek sebenarnya saat runtime, bukan berdasarkan tipe referensi.

3. Berikan contoh kasus polymorphism dalam sistem POS selain produk pertanian.
Jawaban: Contohnya adalah metode hitungTotal() pada berbagai jenis pembayaran seperti tunai, kartu, dan e-wallet yang memiliki implementasi berbeda.

3. [Tuliskan kembali pertanyaan 3 dari panduan]  
   **Jawaban:** …  )
