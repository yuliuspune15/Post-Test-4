⚽ Sistem Manajemen Reservasi Lapangan Futsal (PBO)
Proyek ini adalah implementasi Sistem Manajemen Reservasi Lapangan Futsal berbasis konsol, yang dibangun menggunakan bahasa pemrograman Java. Tujuan utama proyek ini adalah mendemonstrasikan empat pilar utama dari Object-Oriented Programming (OOP): Encapsulation, Inheritance, Abstraction, dan Polymorphism.

Fitur Utama Aplikasi
1. Tambah Reservasi: Mendukung dua jenis reservasi (Reguler dan Member).

2. Tampilkan Semua Reservasi: Menampilkan daftar reservasi, termasuk jenis dan biaya akhir (Polymorphism).

3. Hapus Reservasi: Menghapus data berdasarkan nomor urut.

4. Cek Bentrok: Mencegah reservasi ganda pada waktu dan lapangan yang sama.

Struktur dan Hierarki Kelas
Proyek ini dibagi menjadi tiga package utama (main, model, service) dan memiliki hierarki kelas

Penerapan Konsep Object-Oriented Programming (OOP)
1. Encapsulation (Enkapsulasi)
Tujuan: Melindungi integritas data reservasi.
Implementasi: Semua atribut penting (seperti namaPelanggan, tanggal, nomorLapangan) pada kelas Aktivitas, ReservasiReguler, dan ReservasiMember dideklarasikan sebagai private.
Akses Data: Akses dan modifikasi data hanya dapat dilakukan melalui method public Getter (getNamaPelanggan(), getTanggal()) dan Setter.

2. Inheritance (Pewarisan)
Tujuan: Menggunakan kembali kode dasar reservasi.
Implementasi: Kelas ReservasiReguler dan ReservasiMember extends Aktivitas.
Detail: Kedua subclass mewarisi semua properti dan method dasar dari Aktivitas. Di konstruktor subclass, pemanggilan super(...) memastikan data dasar diinisialisasi oleh Superclass.

3. Abstraction (Abstraksi)
Tujuan: Mendefinisikan kerangka kerja wajib dan menyembunyikan detail perhitungan biaya.
Abstract Class: Kelas Aktivitas dideklarasikan sebagai abstract class dan mengandung method abstrak:
public abstract double hitungBiayaAkhir();
Metode ini wajib diimplementasikan oleh setiap subclass (Member dan Reguler), yang memiliki rumus perhitungan biaya yang berbeda.
Interface: Lapangan dideklarasikan sebagai interface, yang mendefinisikan kontrak fungsionalitas tambahan pada objek lapangan (misalnya, getBiayaTambahan()), yang diimplementasikan oleh LapanganIndoor.

4. Polymorphism (Polimorfisme - Banyak Bentuk)
A. Method Overloading
Implementasi: Diterapkan pada kelas AktivitasService dengan dua method bernama sama:
tambahReservasi(ReservasiReguler reservasi)
tambahReservasi(ReservasiMember reservasi)
Peran: Memungkinkan programmer menggunakan satu nama method (tambahReservasi) untuk menambah dua jenis objek yang berbeda.

B. Run-time Polymorphism (Overriding)
Implementasi:
List data reservasi di AktivitasService dideklarasikan menggunakan tipe ArrayList<Aktivitas> (tipe Superclass).
Kedua subclass (ReservasiReguler dan ReservasiMember) meng-override metode hitungBiayaAkhir().
Peran: Saat iterasi data, ketika aktivitas.hitungBiayaAkhir() dipanggil, Java secara otomatis memanggil implementasi yang benar (dengan diskon untuk Member, tanpa diskon untuk Reguler) pada saat runtime.
