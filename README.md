# Soal 2

### W5 : soal 2

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/soal2.1.jpg"  width="900px">
<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/soal2.2.jpg"  width="900px">

# Soal 3

## Penjalasan

- .substring. Ini bertujuan agar karakter pertama dari data yang ditampilkan di variabel result. Tapi panjang value.body kurang dari data karakter yang pertama, pemanggilan substring dapat menyebabkan error.
- catchError(\_), yang akan menangkap kesalahan seperti koneksi gagal atau respons server bermasalah. Jika terjadi error

### W5 : soal 3

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal3.gif"  width="150px">

# Soal 4

## Penjelasan

Maksud dari langkah 1 dan langkah 2 itu menjalankan tiga fungsi yang masing-masing butuh 3 detik buat ngembaliin angka (1, 2, dan 3). Di dalam fungsi count(), ketiga fungsi ini dipanggil satu per satu pakai await, jadi total waktu yang dibutuhkan 9 detik. Angka yang didapat dijumlahin ke variabel total, terus diubah jadi String dan disimpan di result. Setelah itu, setState() dipanggil supaya UI ikut berubah dan nunjukin hasilnya.

### W5 : soal 4

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal4.gif"  width="150px">

# Soal 5

## Penjelasan

Maksud dari langkah 2 itu pakai Completer<int> buat ngontrol kapan sebuah Future selesai. Pas getNumber() dipanggil, dia bikin Completer, lalu manggil calculate(), dan langsung ngembaliin Future, tapi hasilnya belum ada. Nah, di dalam calculate(), ada delay 5 detik pakai Future.delayed(), baru setelah itu completer.complete(42); dipanggil buat ngasih nilai 42 ke Future tadi. Jadi, harus nunggu dulu hasil dari getNumber() selama 5 detik, baru dapat angka 42.

### W5 : soal 5

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal5.gif"  width="150px">

# Soal 6

## Penjelasan

Perbedaan di Langkah 2 dan Langkah 5–6 ada di cara nanganin errornya. Di Langkah 2, kalau ada masalah saat proses calculate(), aplikasinya bisa error atau ngegantung karena nggak ada penanganan error sama sekali. Sementara di Langkah 5, ada try-catch yang siap menanganin error tersebut dan kasih respon yang sesuai. Terus di Langkah 6, hasilnya ditangani pakai then() kalau sukses, dan catchError() kalau gagal.

### W5 : soal 6

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal6.gif"  width="150px">

# Soal 7

### W5 : soal 7

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal7.gif"  width="150px">

# Soal 8

## Penjelasan

Perbedaan langkah 1 dan langkah 4 adalah cara ngatur proses async (future). Langkah 1 pakai FutureGroup, cocok kalau future-nya ditambah satu-satu secara dinamis, tapi butuh package tambahan dan kodenya agak panjang. Sedangkan langkah 4 pakai Future.wait, simpel banget karena semua future udah siap dari awal, nggak perlu package tambahan, dan langsung jalan barengan. Jadi, kalau future-nya udah lengkap dari awal, mending pakai Future.wait; tapi kalau future-nya muncul belakangan atau dinamis, baru deh pakai FutureGroup.

# Soal 9

### W5 : soal 9

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal9.gif"  width="150px">
