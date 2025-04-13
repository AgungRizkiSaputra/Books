# Praktikum 1

## Soal 1

    @override
      Widget build(BuildContext context) {
        return MaterialApp(
          title: 'Agung',
          theme: ThemeData(
            primarySwatch: Colors.blue,
            visualDensity: VisualDensity.adaptivePlatformDensity,
          ),
          home: const NavigationDialogScreen(),
        );
      }

## Soal 2

### W5 : soal 2

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/soal2.1.jpg"  width="900px">
<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/soal2.2.jpg"  width="900px">

## Soal 3

### Penjalasan

- .substring. Ini bertujuan agar karakter pertama dari data yang ditampilkan di variabel result. Tapi panjang value.body kurang dari data karakter yang pertama, pemanggilan substring dapat menyebabkan error.
- catchError(\_), yang akan menangkap kesalahan seperti koneksi gagal atau respons server bermasalah. Jika terjadi error

### W5 : soal 3

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal3.gif"  width="150px">

# Praktikum 2

## Soal 4

### Penjelasan

Maksud dari langkah 1 dan langkah 2 itu menjalankan tiga fungsi yang masing-masing butuh 3 detik buat ngembaliin angka (1, 2, dan 3). Di dalam fungsi count(), ketiga fungsi ini dipanggil satu per satu pakai await, jadi total waktu yang dibutuhkan 9 detik. Angka yang didapat dijumlahin ke variabel total, terus diubah jadi String dan disimpan di result. Setelah itu, setState() dipanggil supaya UI ikut berubah dan nunjukin hasilnya.

### W5 : soal 4

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal4.gif"  width="150px">

# Praktikum 3

## Soal 5

### Penjelasan

Maksud dari langkah 2 itu pakai Completer<int> buat ngontrol kapan sebuah Future selesai. Pas getNumber() dipanggil, dia bikin Completer, lalu manggil calculate(), dan langsung ngembaliin Future, tapi hasilnya belum ada. Nah, di dalam calculate(), ada delay 5 detik pakai Future.delayed(), baru setelah itu completer.complete(42); dipanggil buat ngasih nilai 42 ke Future tadi. Jadi, harus nunggu dulu hasil dari getNumber() selama 5 detik, baru dapat angka 42.

### W5 : soal 5

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal5.gif"  width="150px">

## Soal 6

### Penjelasan

Perbedaan di Langkah 2 dan Langkah 5–6 ada di cara nanganin errornya. Di Langkah 2, kalau ada masalah saat proses calculate(), aplikasinya bisa error atau ngegantung karena nggak ada penanganan error sama sekali. Sementara di Langkah 5, ada try-catch yang siap menanganin error tersebut dan kasih respon yang sesuai. Terus di Langkah 6, hasilnya ditangani pakai then() kalau sukses, dan catchError() kalau gagal.

### W5 : soal 6

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal6.gif"  width="150px">

# Praktikum 4

## Soal 7

### W5 : soal 7

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal7.gif"  width="150px">

## Soal 8

### Penjelasan

Perbedaan langkah 1 dan langkah 4 adalah cara ngatur proses async (future). Langkah 1 pakai FutureGroup, cocok kalau future-nya ditambah satu-satu secara dinamis, tapi butuh package tambahan dan kodenya agak panjang. Sedangkan langkah 4 pakai Future.wait, simpel banget karena semua future udah siap dari awal, nggak perlu package tambahan, dan langsung jalan barengan. Jadi, kalau future-nya udah lengkap dari awal, mending pakai Future.wait; tapi kalau future-nya muncul belakangan atau dinamis, baru deh pakai FutureGroup.

# Praktikum 5

## Soal 9

### W5 : soal 9

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal9.gif"  width="150px">

## Soal 10

### Penjelasan

Hasilnya itu muncul tulisan "Success". Langkah 1 itu bikin fungsi yang sengaja lempar error setelah nunggu 2 detik, itu kayak buat siimulasi error. Nah, di langkah 4, fungsi itu dipanggil tapi dibungkus pakai try-catch biar errornya bisa diambil dan ditampilin ke UInya pakai setState. Terus, bagian finally tetap jalan buat nunjukin prosesnya udah selesai, entah berhasil atau gagal. Jadi intinya, langkah 1 bikin error, langkah 4 nangkep dan ngatur responnya.

# Praktikum 6

## Soal 11

    @override
    Widget build(BuildContext context) {
      // final myWidget =
      //     myPosition == '' ? const CircularProgressIndicator() : Text(myPosition);

    return Scaffold(
      appBar: AppBar(title: const Text('Agung Rizki Saputra')),
      body: Center(
        child: FutureBuilder(
          future: position,
          builder: (BuildContext context, AsyncSnapshot<Position> snapshot) {
            if (snapshot.connectionState == ConnectionState.waiting) {
              return const CircularProgressIndicator();
            } else if (snapshot.connectionState == ConnectionState.done) {
              if (snapshot.hasError) {
                return Text('Something terrible happened!');
              }
              return Text(snapshot.data.toString());
            }
            return const SizedBox(); // <<--- Tambahan agar tidak error
          },
        ),
      ),
    );
  }

## Soal 12

### Penjelasan

Ya, Saya dapat koordinat GPS saat di run browser itu karna ada await Geolocator.requestPermission(); dimana harus dapat izin dengan benar agar bisa run di browser.

### W5 : soal 12

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal12.gif"  width="150px">

# Praktikum 7

## Soal 13

### Penjelasan

Perbedaanya itu tidak terlalu banyak untuk UInya tapi tidak membutuhkan minta izin akses locationnya lagi, dan juga di tambahkan untuk menunggu selama 3 detik untuk dapetin locationnya.

### W5 : soal 13

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal13.gif"  width="150px">

## Soal 14

### Penjelasan

Tidak ada perbedaan di kodenya cuman hanya menangani error aja kalo hasil UInya sama aja kayak soal no 13

# Praktikum 8

## Soal 15

    @override
      Widget build(BuildContext context) {
        return Scaffold(
          backgroundColor: color,
          appBar: AppBar(title: const Text('Agung Rizki Saputra')),
          body: Center(
            child: ElevatedButton(
              child: const Text('Change Color'),
              onPressed: () {
                _navigateAndGetColor(context);
              },
            ),
          ),
        );
      }

## Soal 16

### Penjelasan

 - navigation_first.dart
   
    pada file ini bikin tampilan layar pertama (class NavigationFirst) pakai StatefulWidget, soalnya ada data yang bisa berubah warna background. Pertama, warna backgroundnya biru. Di tengah layar ada tombol "Change Color", pas di klik, aplikasi akan pindah ke halaman kedua (NavigationSecond). Nah itu dilakukan lewat Navigator.push. Habis dari halaman kedua, aplikasi bisa nerima warna baru dari halaman kedua, terus warna latar halaman pertama diganti pakai warna itu dan ditampilin ulang pakai setState. Kalau halaman kedua ga ngasih warna apa-apa, maka balik ke warna biru default.

 - navigation_second.dart

   pada file ini bikin halaman kedua (NavigationSecond) pakai StatefulWidget. Di dalamnya ada tiga tombol: Merah, Hijau, dan Biru. Pas user klik salah satu tombol itu, kode di onPressed bakal nyimpen warna yang sesuai pakai color = Colors.red.shade700, misalnya, terus halaman ini ditutup pakai Navigator.pop, sambil ngirim balik warna itu ke halaman pertama. Warna yang dikirim ini nanti dipakai buat ganti background halaman sebelumnya. Variabel color sendiri dideklarasiin di dalam build, dan langsung diisi sebelum dikirim balik ke halaman pertama.


### W5 : soal 16

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal16.gif"  width="150px">

# Praktikum 9

## Soal 17

### Penjelasan

pada bagian ini bikin tampilan layar (class NavigationDialogScreen) yang pakai StatefulWidget karena warna backgroundnya bisa berubah. Fungsi utamanya itu nampilin dialog saat tombol "Change Color" dipencet. Dialog ini berupa AlertDialog yang ngasih pilihan ke user buat milih salah satu dari tiga warna: Merah, Hijau, atau Biru. Pas salah satu tombol dipencet, dialog ditutup pakai Navigator.pop, sambil ngirim warna yang dipilih. Warna itu langsung dipakai buat ngubah warna latar belakang halaman utama, dan supaya perubahan warnanya muncul di layar, dipanggil setState().

### W5 : soal 17

<img src="https://github.com/AgungRizkiSaputra/Books/blob/main/images/GIFsoal17.gif"  width="150px">
   
