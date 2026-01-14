# Laporan Praktikum Minggu 1 (sesuaikan minggu ke berapa?)
Topik: UML dan Prinsip Solid

## Identitas
- Nama  : Inayah Fijanatin
- NIM   : 240202908
- Kelas : 3IKKA

---

## Tujuan
(Tuliskan tujuan praktikum minggu ini.) 
Tujuan dari praktikum ini adalah agar mahasiswa mampu memahami dan menerapkan Unified Modeling Language (UML) dalam perancangan sistem serta memahami penerapan prinsip SOLID pada desain perangkat lunak berorientasi objek agar sistem yang dibangun menjadi terstruktur, mudah dikembangkan, dan mudah dipelihara.
---

## Dasar Teori
1. UML (Unified Modeling Language) adalah bahasa pemodelan standar untuk memvisualisasikan, merancang, dan mendokumentasikan sistem perangkat lunak.
2. Use Case Diagram digunakan untuk menggambarkan interaksi antara aktor dan sistem.
3. Activity Diagram menggambarkan alur aktivitas atau proses bisnis dalam sistem.
4. Sequence Diagram menunjukkan urutan interaksi antar objek dalam suatu proses.
5. Prinsip SOLID adalah kumpulan prinsip desain OOP yang bertujuan menghasilkan kode yang fleksibel dan mudah dirawat.
---

## Langkah Praktikum
1. Menganalisis kebutuhan sistem (studi kasus sistem POS sederhana).
2. Menentukan aktor dan fungsionalitas sistem.
3. Membuat diagram UML yang terdiri dari:
   - Use Case Diagram
   - Activity Diagram
   - Sequence Diagram
   - Class Diagram
4. Menganalisis penerapan prinsip SOLID pada desain class.
5. Menjalankan program contoh untuk memastikan struktur class dapat dieksekusi dengan baik.
6. Menyimpan hasil pekerjaan dan melakukan commit ke repository dengan pesan:
add uml design and solid analysis

---

## Kode Program

---

## Hasil Eksekusi
(JPG) di SS
---

## Analisis
- Program berjalan dengan memanfaatkan interface sebagai penghubung antara service dan implementasi pembayaran.
- Pendekatan minggu ini berbeda dengan minggu sebelumnya karena fokus pada desain sistem dan pemodelan UML, bukan hanya implementasi kode.
- Kendala yang dihadapi adalah error cannot find symbol akibat interface belum dibuat atau package tidak sesuai. Kendala tersebut diatasi dengan membuat interface pada package yang benar dan memperbaiki struktur folder.

## Kesimpulan
Berdasarkan praktikum ini, dapat disimpulkan bahwa penggunaan UML membantu dalam memahami dan merancang sistem secara visual, sedangkan penerapan prinsip SOLID membuat desain class lebih fleksibel, terstruktur, dan mudah dikembangkan di masa mendatang.
---

## Quiz
1. Apa fungsi Use Case Diagram?
Jawaban:
Use Case Diagram berfungsi untuk menggambarkan interaksi antara aktor dan sistem serta menunjukkan fungsionalitas yang disediakan oleh sistem.

2. Sebutkan salah satu prinsip SOLID dan jelaskan!
Jawaban:
Single Responsibility Principle (SRP) menyatakan bahwa satu class hanya boleh memiliki satu tanggung jawab atau satu alasan untuk berubah.

3. Mengapa interface penting dalam penerapan SOLID?
Jawaban:
Interface penting karena memungkinkan sistem bergantung pada abstraksi, bukan implementasi konkret, sehingga memudahkan pengembangan dan perubahan fitur tanpa merusak kode yang sudah ada.

3. [Tuliskan kembali pertanyaan 3 dari panduan]  
   **Jawaban:** …  )
