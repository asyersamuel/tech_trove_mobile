# Tech Trove

Asyer Samuel Marpaung
2306165925

<details>
  <summary>TUGAS 7</summary>

**Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.**

**Stateless Widget** adalah widget yang sifatnya statis, artinya tampilannya tidak berubah selama aplikasi berjalan. Setelah Stateless Widget dibuat, ia tidak memiliki kemampuan untuk memperbarui atau mengubah dirinya sendiri.

**Stateful Widget** adalah widget yang dinamis, yang dapat berubah-ubah seiring berjalannya aplikasi. Stateful Widget memiliki "state" atau kondisi yang memungkinkan tampilan dan data di dalamnya untuk diperbarui kapan saja. Misalnya, ketika pengguna berinteraksi dengan komponen yang memiliki aksi seperti tombol yang mengubah nilai, bidang input yang menerima teks, atau tampilan yang berubah berdasarkan data baru, Stateful Widget adalah pilihan yang tepat.

Secara sederhana, perbedaan utama antara Stateless dan Stateful Widget adalah pada kemampuannya untuk berubah: Stateless Widget bersifat tetap dan tidak dapat berubah setelah dibuat, sedangkan Stateful Widget memiliki kondisi yang dapat berubah seiring waktu, memungkinkan UI yang lebih dinamis dan interaktif.

**Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.**

- **Scaffold**: Menyediakan struktur dasar untuk halaman, termasuk area untuk AppBar dan body. Ini membantu dalam membangun layout yang konsisten di seluruh aplikasi.
- **AppBar**: Widget ini digunakan untuk menampilkan bagian atas halaman, termasuk judul aplikasi ("Tech Trove") dan warna latar belakang yang diambil dari tema.
- **Container**: Digunakan untuk mengatur warna latar belakang dan padding dari area body. Ini juga dapat berfungsi untuk membungkus widget lain dengan ukuran atau margin tertentu.
- **Column**: Menyusun widget anak secara vertikal. Dalam proyek ini, digunakan untuk menyusun elemen seperti InfoCard dan GridView.
- **Row**: Menyusun widget anak secara horizontal. Di sini, digunakan untuk menampilkan tiga InfoCard secara berdampingan.
- **SizedBox**: Memberikan ruang kosong antara widget. Dalam proyek ini, digunakan untuk memberikan jarak vertikal antara elemen.
- **Center**: Memposisikan widget anak di tengah area yang tersedia. Di sini, digunakan untuk menempatkan kolom yang berisi teks sambutan dan grid item.
- **Padding**: Menambahkan ruang di sekitar widget. Digunakan di sekitar teks untuk memberikan jarak yang nyaman.
- **GridView**: Menyediakan tampilan grid untuk menampilkan item. Dalam proyek ini, digunakan untuk menampilkan ItemCard dalam format grid dengan tiga kolom.
- **Card**: Widget yang digunakan untuk menampilkan konten dengan efek bayangan, memberi tampilan yang lebih menarik dan terpisah dari latar belakang.
- **Text**: Digunakan untuk menampilkan teks. Terdapat beberapa instance di mana widget ini digunakan, termasuk judul kartu dan teks sambutan.
- **Icon**: Menampilkan ikon dalam ItemCard. Di sini, ikon digunakan untuk merepresentasikan setiap item di dalam grid.
- **Material**: Memberikan material design yang dapat mengubah warna latar belakang dan memberikan efek visual seperti sudut melengkung.
- **InkWell**: Menambahkan efek ripple ketika kartu ditekan. Ini memberikan umpan balik visual kepada pengguna saat mereka berinteraksi dengan kartu.
- **SnackBar**: Digunakan untuk menampilkan pesan sementara di bagian bawah layar saat pengguna menekan kartu. Ini memberikan umpan balik yang jelas tentang interaksi.
- **ItemHomepage**: Kelas ini digunakan untuk merepresentasikan data untuk setiap item di dalam grid, termasuk nama, ikon, dan warna.

**Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.**

Fungsi setState() pada Flutter digunakan untuk memberitahukan framework bahwa ada perubahan pada state yang perlu diperbarui dalam tampilan (UI). Ketika setState() dipanggil, Flutter akan merender ulang widget yang terpengaruh sehingga UI aplikasi dapat menampilkan perubahan terbaru sesuai dengan data baru pada state.

_Variabel yang Terdampak oleh setState()_

Variabel-variabel yang berada dalam class State dari StatefulWidget dan diubah di dalam setState() akan memengaruhi tampilan. Berikut adalah contoh variabel yang umumnya terdampak:

1.  Variabel State Internal

- Contohnya: int counter, bool isVisible, String text, List items, dll.
- Variabel ini adalah data yang menentukan tampilan widget. Misalnya, jika kita mengubah nilai counter di dalam setState(), tampilan yang menampilkan nilai counter akan di-render ulang.

2.  Variabel yang Mengubah Kondisi UI

- Contohnya: Color backgroundColor, double fontSize, dll.
- Jika variabel-variabel ini diubah, setState() akan membuat tampilan bereaksi terhadap perubahan tersebut, misalnya mengubah warna atau ukuran font di UI.

3.  Variabel yang Mengontrol Interaksi Pengguna

- Contohnya: bool isLoading, bool isButtonEnabled, String buttonText, dll.
- Ini adalah variabel yang mungkin menentukan apakah tombol diaktifkan, teks tombol berubah, atau indikator loading ditampilkan. Dengan setState(), UI akan mencerminkan perubahan status dari variabel-variabel ini.

**Jelaskan perbedaan antara const dengan final.**

Di Flutter, const dan final digunakan untuk mendefinisikan variabel yang nilainya tidak bisa diubah, tetapi keduanya memiliki perbedaan kapan nilainya ditetapkan. Kata kunci const digunakan ketika nilai variabel sudah diketahui dan akan tetap sama sepanjang aplikasi berjalan. Nilai ini harus ditentukan saat kompilasi (compile-time), sehingga cocok untuk data yang benar-benar konstan, seperti angka tetap atau teks statis. Sementara itu, final digunakan ketika nilai variabel baru bisa diketahui saat aplikasi berjalan (runtime) dan tetap tidak dapat diubah setelah itu. final ideal untuk data yang tidak bisa diinisialisasi pada saat kompilasi tetapi tetap stabil setelahnya.

**Jelaskan bagaimana cara kamu mengimplementasikan checklist-checklist di atas.**

- **Membangun Struktur Utama Aplikasi**
  Pertama membuat widget MyHomePage, yang menjadi halaman utama aplikasi ini. Pada tahap ini, saya memastikan atribut penting, seperti npm, name, dan className, tersimpan dengan baik di dalam widget tersebut. Saya juga membuat daftar items, yang berisi instance ItemHomepage untuk setiap tombol yang diperlukan: "Lihat Daftar Produk," "Tambah Produk," dan "Logout." Saya ingin setiap tombol tampil dengan ikon, teks, dan warna yang berbeda. Struktur Scaffold, untuk memberikan tata letak dasar yang lengkap dengan AppBar dan body, sehingga halaman utama aplikasi dapat tersusun dengan baik.

- **Penambahan InfoCard untuk Informasi Dasar Pengguna**
  Saya membuat kelas InfoCard yang menampilkan NPM, Name, dan Class di bagian atas halaman dalam format tiga kartu secara horizontal. Setiap InfoCard dirancang untuk menerima judul (title) dan konten (content), yang disesuaikan dengan informasi pengguna. Dalam InfoCard, saya menggunakan Card dengan elevation untuk menambahkan efek bayangan ringan. Selain itu, saya mengatur lebar kartu menggunakan MediaQuery, yang membuat tampilan lebih responsif dan menggunakan Row dengan mainAxisAlignment spaceEvenly memudahkan dalam memastikan setiap kartu memiliki jarak yang merata di layar.

- **Merancang Tombol Interaktif dengan ItemHomepage dan ItemCard**
  Untuk bagian daftar tombol, saya menggunakan GridView.count dengan crossAxisCount 3 agar tiga tombol dapat ditampilkan dalam satu baris. Setiap tombol dikendalikan oleh ItemHomepage, yang menyimpan atribut nama (name), ikon (icon), dan warna (color). Dengan begitu, setiap tombol memiliki tampilan dan fungsi yang berbeda sesuai dengan arahan di checklist. Kemudian, saya membuat widget ItemCard yang menerima objek ItemHomepage dan menampilkan setiap tombol dalam bentuk kartu dengan ikon dan teks yang berada di tengah. Dalam ItemCard, saya menggunakan Material dan InkWell untuk memastikan tampilan warna yang konsisten dan memberikan animasi ketika tombol ditekan.

- **Mengimplementasikan Snackbar untuk Respon Tekan Tombol**
  Sesuai dengan checklist, saya menambahkan interaksi untuk setiap tombol menggunakan Snackbar. Saya membuat fungsi onTap pada setiap tombol di ItemCard, di mana ScaffoldMessenger.of(context).showSnackBar digunakan untuk menampilkan pesan. Saya memastikan Snackbar menampilkan teks dinamis berdasarkan tombol yang ditekan, menggunakan nilai dari item. name . Saya menambahkan hideCurrentSnackBar() sebelum menampilkan yang baru, untuk menghindari tampilan Snackbar yang menumpuk.

- **Membuat Kelas ItemHomepage sebagai Model Data Tombol**
Saya membuat kelas ItemHomepage untuk menyimpan atribut utama dari setiap tombol, yaitu nama, ikon, dan warna, agar lebih mudah untuk menambahkan atau mengedit tombol dengan atribut yang jelas tanpa perlu mengubah tampilan tombol secara langsung di MyHomePage.
</details>

<details>
  <summary>TUGAS 8</summary>

**Apa kegunaan const di Flutter? Jelaskan apa keuntungan ketika menggunakan const pada kode Flutter. Kapan sebaiknya kita menggunakan const, dan kapan sebaiknya tidak digunakan?**

Di Flutter, const digunakan untuk mendeklarasikan nilai konstan yang tidak akan berubah selama runtime aplikasi. Ini bisa diaplikasikan pada widget atau variabel yang tetap sama sepanjang waktu, membantu Flutter menghindari proses rebuild yang tidak perlu. Sebagai contoh, jika kita membuat sebuah widget statis seperti Text atau Icon yang tidak bergantung pada data dinamis, kita bisa mendeklarasikannya sebagai const. Dengan begitu, Flutter tahu bahwa widget tersebut bisa di-cache dan tidak perlu di-render ulang setiap kali antarmuka aplikasi di-refresh.

Menggunakan const memberikan keuntungan pada performa aplikasi. Dengan const, Flutter dapat menghemat penggunaan memori dan waktu komputasi, karena objek const hanya dibuat satu kali di memori dan dapat digunakan ulang tanpa perlu membuat objek baru setiap kali widget tersebut digunakan. Ini membuat aplikasi lebih efisien, terutama ketika ada banyak widget statis dalam antarmuka.

const sebaiknya digunakan pada widget atau variabel yang tidak akan berubah atau tidak perlu di-update berdasarkan kondisi tertentu, seperti teks atau ikon statis, atau layout yang sifatnya tetap. Dan penggunaan const perlu dihindari pada widget yang bergantung pada data dinamis atau state yang berubah-ubah.

**Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!**

Column dan Row adalah widget dasar di Flutter yang digunakan untuk mengatur tata letak widget anak dalam bentuk vertikal dan horizontal. Column menyusun widget anak dalam satu arah ke bawah (vertikal), sedangkan Row menyusun widget anak secara mendatar (horizontal). Keduanya berguna untuk membuat tata letak sederhana yang fleksibel dan responsif.

Dalam penggunaan Column, widget ini cocok ketika kita ingin menampilkan elemen-elemen secara bertumpuk, seperti membuat daftar vertikal atau formulir. Kita bisa menyesuaikan alignment, padding, dan jarak antar-elemen di dalam Column untuk menghasilkan tampilan yang sesuai dengan kebutuhan. Contoh umum penggunaan Column adalah menampilkan elemen-elemen seperti judul, teks paragraf, dan tombol yang disusun ke bawah.

Row digunakan untuk menyusun elemen-elemen secara sejajar di dalam satu baris. Ini berguna ketika kita ingin membuat tata letak yang memerlukan penempatan elemen-elemen berdampingan, seperti ikon dan teks atau beberapa tombol dalam satu baris. Dengan Row, kita bisa mengatur alignment elemen ke kiri, tengah, atau kanan, serta mengatur spacing antar-widget anak.

Contoh Implementasi Column:

```
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  children: [
    Text("Welcome to Flutter"),
    Text("This is a Column example"),
    ElevatedButton(onPressed: () {}, child: Text("Press Me")),
  ],
);
```

Contoh Implementasi Row:

```
Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Icon(Icons.home),
    Text("Home"),
    ElevatedButton(onPressed: () {}, child: Text("Settings")),
  ],
);
```

Dalam contoh di atas, Column menyusun elemen dari atas ke bawah, sementara Row menempatkannya dari kiri ke kanan.

**Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!**

Pada halaman form saya, elemen input yang digunakan adalah TextFormField. Elemen ini digunakan untuk menerima input dari pengguna pada beberapa field, yaitu Name, Amount, Price, dan Description. Setiap TextFormField memiliki atribut labelText, hintText, dan border, serta divalidasi untuk memastikan input yang benar. Misalnya, Amount dan Price divalidasi agar hanya menerima angka, sementara Name dan Description divalidasi agar tidak kosong dan memiliki panjang minimum tertentu.

Selain TextFormField, Flutter memiliki beberapa elemen input lainnya yang tidak digunakan pada tugas saya tersebut, seperti Checkbox, Radio, Switch, dan Slider. Checkbox cocok untuk pilihan ya atau tidak, seperti ketika pengguna diminta untuk menyetujui syarat dan ketentuan atau memilih lebih dari satu opsi. Radio digunakan untuk memilih satu dari beberapa opsi yang telah ditentukan, misalnya untuk memilih kategori produk atau status tertentu. Switch sering digunakan untuk pilihan on/off, seperti mengaktifkan atau menonaktifkan fitur tertentu dalam aplikasi, misalnya mengaktifkan notifikasi atau dark mode. Slider digunakan untuk memilih nilai dalam rentang tertentu, seperti menentukan harga atau jumlah suatu item dengan cara yang lebih interaktif dan visual.

**Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?**

Untuk mengatur tema dalam aplikasi Flutter agar konsisten, saya menggunakan fitur ThemeData yang disediakan oleh Flutter. Dengan ThemeData, saya dapat menentukan elemen-elemen visual dasar aplikasi, seperti warna latar belakang, warna teks, dan gaya widget, secara keseluruhan. Penggunaan tema yang terpusat ini membuat perubahan pada tampilan aplikasi dapat dilakukan dengan lebih mudah dan konsisten tanpa perlu mengubah setiap elemen satu per satu.

Pada aplikasi yang saya buat, saya mengimplementasikan tema yang diatur di dalam widget MyApp menggunakan ThemeData. Saya menggunakan ColorScheme untuk mengatur warna utama aplikasi, yaitu warna cyan untuk primary, warna ungu untuk secondary, dan warna abu-abu muda untuk latar belakang aplikasi (background). Dengan pengaturan ini, seluruh aplikasi akan mengikuti skema warna yang telah ditentukan tanpa perlu mengatur warna secara manual pada setiap widget.

Selain itu, saya juga mengaktifkan useMaterial3: true di dalam tema, yang mengaktifkan desain Material You di aplikasi. Ini memberikan tampilan dan nuansa yang lebih modern serta responsif terhadap preferensi pengguna.

**Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?**

Dalam aplikasi Flutter yang memiliki banyak halaman, navigasi dapat dikelola menggunakan widget Navigator yang memungkinkan pengguna berpindah antar halaman dengan cara yang terstruktur. Saya menggunakan Navigator untuk menangani navigasi di aplikasi, baik untuk perpindahan halaman yang bersifat sementara (push) maupun menggantikan halaman yang sedang aktif (pushReplacement), untuk kembali ke halaman sebelumnya (pop). Ini memungkinkan pengguna untuk berinteraksi dengan berbagai bagian aplikasi dengan cara yang terorganisir.

Dalam kasus aplikasi yang saya buat, navigasi antar halaman dikendalikan melalui menu samping atau drawer. Pada kode yang saya buat, drawer terdiri dari beberapa ListTile, yang masing-masing mewakili halaman berbeda di aplikasi. Misalnya, terdapat item yang mengarahkan pengguna ke halaman utama MyHomePage, dan item yang mengarahkan ke halaman form untuk menambahkan produk, yaitu ProductEntryFormPage.

Untuk menangani navigasi, saya menggunakan metode Navigator.push, Navigator.pushReplacement, dan Navigator.pop. Pada item ListTile yang pertama, ketika pengguna memilih "Halaman Utama", saya menggunakan Navigator.pushReplacement untuk mengganti halaman yang aktif saat itu dengan MyHomePage, yang berfungsi menghilangkan halaman sebelumnya dari stack navigasi. Sedangkan untuk item "Tambah Product", saya menggunakan Navigator.push untuk memulai navigasi ke halaman baru (ProductEntryFormPage) tanpa menghapus halaman sebelumnya dari stack, dan Navigator.pop untuk menutup halaman saat pengguna selesai atau ingin kembali ke halaman sebelumnya

</details>
