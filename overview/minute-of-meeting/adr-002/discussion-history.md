# Discussion History

## Penambahan Kolom Tag untuk Aktivitas Check In, Check Out, Step In, dan Step Out

#### Topik

Penambahan Kolom Tag untuk Aktivitas Check In, Check Out, Step In, dan Step Out

#### Masalah

User membutuhkan laporan attendance yang dapat dihasilkan secara otomatis dari aplikasi Checkin. Selain itu, sistem perlu mendukung pencatatan aktivitas **Check In, Check Out, Step In, dan Step Out**.

Terdapat kebutuhan untuk menampilkan seluruh aktivitas tersebut dalam laporan tanpa melakukan perubahan besar pada halaman atau form utama Checkin.

#### Keputusan

Menambahkan fitur **Tag** untuk mengidentifikasi jenis aktivitas attendance, yaitu:

* Check In
* Check Out
* Step In
* Step Out

Data aktivitas yang telah diberi tag akan ditampilkan pada halaman **Report** untuk menghasilkan laporan attendance secara otomatis.

Dengan pendekatan ini, proses pada halaman Checkin dapat tetap sederhana, sementara pengelompokan dan identifikasi jenis aktivitas dilakukan berdasarkan tag yang tersimpan pada data attendance.

#### Kelebihan

* Meminimalkan perubahan pada form atau halaman utama Checkin.
* Meminimalkan dampak perubahan terhadap aplikasi Checkin yang sudah berjalan.
* Sesuai dengan business flow aktivitas attendance, yaitu Check In, Check Out, Step In, dan Step Out.
* Data dapat digunakan secara terstruktur pada halaman Report berdasarkan jenis aktivitas.
* Memudahkan pengembangan laporan karena setiap aktivitas memiliki identifikasi atau tag yang jelas.

#### Kekurangan

* User perlu melakukan beberapa aktivitas attendance secara terpisah dalam satu hari, yaitu Check In, Check Out, Step In, dan Step Out sesuai dengan aktivitas yang dilakukan.
* Apabila user melakukan Step Out dan Step In beberapa kali dalam satu hari, jumlah transaksi attendance yang tercatat akan semakin banyak.
* User perlu memahami perbedaan fungsi antara Check In, Check Out, Step In, dan Step Out agar tidak terjadi kesalahan pencatatan.
* Sistem perlu memastikan setiap aktivitas memiliki urutan dan pasangan data yang valid, misalnya **Step Out harus memiliki Step In setelahnya**.

#### Alasan

Keputusan ini diambil untuk **meminimalkan biaya dan effort perubahan pada aplikasi Checkin**.

Dengan menggunakan mekanisme Tag, sistem dapat membedakan jenis aktivitas attendance tanpa memerlukan perubahan besar pada struktur atau flow utama aplikasi. Pendekatan ini juga memungkinkan data Check In, Check Out, Step In, dan Step Out digunakan secara terstruktur untuk kebutuhan reporting.

Selain itu, pemisahan aktivitas berdasarkan Tag memungkinkan sistem untuk tetap fleksibel dalam mengembangkan kebutuhan reporting di masa mendatang tanpa harus mengubah secara signifikan proses attendance yang sudah berjalan



## Penggunaan Button untuk Aktivitas Attendance

#### Topic

Penggantian Fungsi Tag dengan Button untuk Aktivitas Check In, Check Out, Step In, dan Step Out

#### Problem / Background

User membutuhkan data aktivitas **Check In, Check Out, Step In, dan Step Out** yang dapat digunakan untuk kebutuhan reporting.

Pada desain awal, jenis aktivitas attendance diidentifikasi menggunakan **Tag**. Namun, pendekatan tersebut berpotensi meningkatkan kompleksitas proses query dan pengolahan data ketika sistem perlu menghasilkan laporan dengan volume data yang besar.

Untuk meningkatkan efisiensi pengambilan data dan scalability sistem, diperlukan perubahan pendekatan dalam pencatatan jenis aktivitas attendance.

#### Decision

Mengganti penggunaan **Tag** dengan **Button** sebagai mekanisme utama untuk melakukan aktivitas:

* Check In
* Check Out
* Step In
* Step Out

Setiap aktivitas yang dilakukan melalui button akan dicatat secara langsung sesuai dengan jenis aktivitasnya sehingga data dapat diproses dan digunakan secara lebih efisien untuk kebutuhan reporting.

#### Kelebihan

* Mempermudah proses query dan pengambilan data untuk kebutuhan reporting.
* Meningkatkan performa saat menampilkan data pada halaman List Report.
* Struktur data lebih terarah berdasarkan jenis aktivitas attendance.
* Sistem lebih scalable untuk menangani pertumbuhan volume data.
* Mengurangi kompleksitas logic dalam proses filtering dan reporting.

#### Kekurangan

* Membutuhkan perubahan dari desain awal yang sebelumnya menggunakan mekanisme Tag.
* Membutuhkan penyesuaian pada database, UI, dan logic sistem.
* Membutuhkan tambahan effort development dan testing.

#### Reasoning

Perubahan ini dilakukan untuk meningkatkan **scalability dan efisiensi pengolahan data**.

Dengan mencatat aktivitas attendance secara langsung berdasarkan jenis aktivitas melalui Button, sistem dapat melakukan query dan menghasilkan report dengan lebih efisien, terutama ketika volume data attendance meningkat.

