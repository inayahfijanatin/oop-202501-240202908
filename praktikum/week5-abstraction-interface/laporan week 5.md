# Laporan Praktikum Minggu 1 (sesuaikan minggu ke berapa?)
Topik: week5-abstraction-interface

## Identitas
- Nama  : Inayah Fijanatin
- NIM   : 240202908
- Kelas : 3IKKA

---

## Tujuan
1. Mahasiswa memahami konsep abstraction dalam Pemrograman Berorientasi Objek.
2. Mahasiswa mampu membedakan penggunaan abstract class dan interface.
3. Mahasiswa mampu mengimplementasikan abstract class, interface, dan multiple inheritance melalui interface.
4. Mahasiswa mampu menerapkan konsep abstraksi pada studi kasus sistem pembayaran Agri-POS.
---

## Dasar Teori
(Tuliskan ringkasan teori singkat (3–5 poin) yang mendasari praktikum.  
1. Abstraction adalah konsep OOP untuk menyembunyikan detail implementasi dan hanya menampilkan fungsi penting.
2. Abstract class tidak dapat diinstansiasi dan dapat memiliki method abstrak maupun konkrit.
3. Interface berisi kontrak method yang harus diimplementasikan oleh class yang menggunakannya.
4. Java tidak mendukung multiple inheritance antar class, tetapi mendukungnya melalui interface.
5. Abstraksi membuat program lebih fleksibel, terstruktur, dan mudah dikembangkan.
---

## Langkah Praktikum
(Tuliskan Langkah-langkah dalam prakrikum)
1. Membuat abstract class Pembayaran dengan method abstrak biaya() dan prosesPembayaran().
2. Membuat interface Validatable untuk validasi pembayaran dan interface Receiptable untuk mencetak struk.
3. Membuat class Cash yang mewarisi Pembayaran dan mengimplementasikan Receiptable.
4. Membuat class EWallet yang mewarisi Pembayaran dan mengimplementasikan dua interface (Validatable dan Receiptable).
5. Membuat MainAbstraction.java untuk menjalankan dan mendemonstrasikan konsep abstraksi dan polimorfisme.
6. Menjalankan program dan mengambil screenshot hasil eksekusi.
7. Melakukan commit dengan pesan week5-abstraction-interface.

---

## Kode Program
(Tuliskan kode utama yang dibuat, (MainAbstraction)  

```java

Pembayaran cash = new Cash("INV-001", 100000, 120000);
Pembayaran ewallet = new EWallet("INV-002", 150000, "user@ewallet", "123456");

System.out.println(((Receiptable) cash).cetakStruk());
System.out.println(((Receiptable) ewallet).cetakStruk());

---

## Hasil Eksekusi
(Sertakan screenshot hasil eksekusi program.  
Program berhasil dijalankan dan menampilkan hasil proses pembayaran serta struk pembayaran sesuai metode yang digunakan.
ada di lampiran Screenshoot

## Analisis
- Program berjalan dengan memanfaatkan abstract class Pembayaran sebagai parent untuk berbagai metode pembayaran.
- Method biaya() dan prosesPembayaran() dipanggil secara polimorfik sesuai jenis objek (Cash atau EWallet).
- Dibandingkan minggu sebelumnya (polymorphism), minggu ini lebih menekankan pada perancangan kontrak dan abstraksi.
- Kendala yang dihadapi adalah kesalahan package dan interface tidak terbaca, yang diatasi dengan memperbaiki struktur folder dan package declaration.

## Kesimpulan
Dari praktikum minggu ke-5 ini dapat disimpulkan bahwa penggunaan abstract class dan interface membantu menyederhanakan kompleksitas program, meningkatkan fleksibilitas, serta memungkinkan penerapan multiple inheritance secara aman dalam Java.

## Quiz
1. Jelaskan perbedaan konsep dan penggunaan abstract class dan interface.
Jawaban: Abstract class digunakan untuk berbagi state dan perilaku dasar, sedangkan interface digunakan untuk mendefinisikan kontrak method tanpa implementasi dan mendukung multiple inheritance.

2. Mengapa multiple inheritance lebih aman dilakukan dengan interface pada Java?
Jawaban: Karena interface tidak memiliki state sehingga menghindari konflik pewarisan yang biasa terjadi pada multiple inheritance antar class.

3. Pada contoh Agri-POS, bagian mana yang paling tepat menjadi abstract class dan mana yang menjadi interface? Jelaskan alasannya.
Jawaban: Pembayaran paling tepat menjadi abstract class karena memiliki atribut dan perilaku umum, sedangkan Validatable dan Receiptable paling tepat menjadi interface karena bersifat kontrak yang dapat digunakan oleh berbagai jenis pembayaran.
