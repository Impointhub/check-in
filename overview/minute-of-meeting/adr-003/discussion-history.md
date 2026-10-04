# Discussion history

## Penampilan Notes untuk Seluruh Aktivitas Attendance pada Report

#### Topic

Menampilkan Notes untuk Aktivitas Check In, Check Out, Step In, dan Step Out pada Halaman Report

#### Problem / Background

Tim HC membutuhkan informasi **Notes** pada report attendance. Namun, setiap aktivitas attendance, yaitu **Check In, Check Out, Step In, dan Step Out**, memiliki kolom Notes masing-masing pada database.

Diperlukan keputusan mengenai bagaimana seluruh informasi Notes tersebut ditampilkan pada halaman Report agar data tetap eksplisit dan mudah ditelusuri.

#### Decision

Menampilkan seluruh kolom Notes dari setiap aktivitas **Check In, Check Out, Step In, dan Step Out** pada halaman Report.

Dengan pendekatan ini, user dapat melihat dan memfilter data berdasarkan aktivitas yang dibutuhkan tanpa kehilangan informasi dari aktivitas attendance lainnya.

* Kelebihan
  * Menampilkan data secara eksplisit sesuai dengan aktivitas attendance yang dilakukan.
  * User dapat melihat seluruh informasi Notes dari Check In, Check Out, Step In, dan Step Out.
  * Memudahkan user melakukan filtering dan penelusuran data sesuai kebutuhan.
  * Mengurangi risiko kehilangan konteks atau informasi dari aktivitas attendance tertentu.
* Kekurangan
  * Tampilan report dapat menjadi lebih kompleks atau overwhelming apabila user memiliki banyak aktivitas Step In dan Step Out dalam satu periode.
  * Membutuhkan pengelolaan tampilan dan filtering yang baik agar informasi tetap mudah dibaca.

#### Reasoning

Keputusan ini diambil untuk memastikan seluruh informasi aktivitas attendance dapat ditampilkan secara **eksplisit, transparan, dan mudah ditelusuri**, sehingga user dapat mengakses data sesuai dengan kebutuhan operasional dan audit.

## Implementasi Report untuk Project Checkin

#### Topic

Implementasi Report untuk Project Checkin

#### Problem / Background

Tim HR membutuhkan sistem yang dapat menghitung dan menampilkan **total jam kerja karyawan secara otomatis**.

Saat ini, proses perhitungan jam kerja masih dilakukan secara manual oleh tim HR dengan cara melakukan export data dari platform Checkin, kemudian data tersebut diolah untuk mendapatkan total jam kerja karyawan.

Selain kebutuhan perhitungan jam kerja, terdapat beberapa kebutuhan lain yang perlu difasilitasi oleh sistem, yaitu:

* Mengotomatisasi pencatatan aktivitas **Step Out** dan **Step In**.
* Mengurangi durasi jam kerja berdasarkan durasi Step Out yang dilakukan oleh karyawan.
* Menyediakan rekap detail aktivitas Step Out dan Step In.
* Menyimpan informasi aktivitas Step Out dan Step In sebagai dokumentasi yang dapat digunakan untuk kebutuhan audit.
* Mengurangi proses pengolahan data secara manual oleh tim HR.

Diperlukan keputusan mengenai pendekatan implementasi report dan penyimpanan data yang paling sesuai dengan kebutuhan HR serta mempertimbangkan effort dan biaya development.

***

#### Option

#### Option 1 – Melakukan Perubahan Database Checkin untuk Mendukung Kebutuhan Reporting HR

Melakukan perubahan dan penambahan struktur database pada aplikasi Checkin untuk menyimpan data yang dibutuhkan oleh HR, termasuk data terkait jam kerja, Step Out, dan Step In.

Data kemudian digunakan sebagai sumber utama untuk menghasilkan report HR.

**Kelebihan**

* Dapat secara langsung memfasilitasi kebutuhan reporting dan perubahan kebutuhan HR.
* Data tersimpan secara terstruktur sehingga proses pengolahan dan perhitungan report menjadi lebih mudah.
* Memungkinkan pengembangan report yang lebih fleksibel karena data sudah tersedia dalam struktur database yang sesuai.
* Memudahkan proses query dan pengolahan data apabila volume data semakin besar.
* Data aktivitas Step Out dan Step In dapat dikelola secara lebih terstruktur untuk kebutuhan audit.

**Kekurangan**

* Membutuhkan perubahan yang cukup besar pada struktur database aplikasi Checkin.
* Membutuhkan effort development yang lebih tinggi untuk perubahan database, backend, dan kemungkinan perubahan pada aplikasi yang sudah berjalan.
* Membutuhkan proses migrasi atau penyesuaian terhadap data existing apabila terdapat perubahan struktur database.
* Membutuhkan effort testing yang lebih besar untuk memastikan perubahan tidak berdampak pada fitur Checkin yang sudah berjalan.
* Biaya development menjadi lebih tinggi.

***

#### Option 2 – Perhitungan Dilakukan pada Modul Report

Sistem perhitungan jam kerja dan rekap aktivitas Step Out dan Step In dilakukan secara langsung pada modul **Report**.

Report yang dikembangkan meliputi:

* **Laporan Jam Kerja**
* **Laporan Rekap Step Out dan Step In**

Rumus perhitungan akan diproses ketika report dibuat atau ditampilkan. Data hasil perhitungan dan rekap yang dibutuhkan akan dikelola pada modul report tanpa melakukan perubahan besar pada struktur database utama aplikasi Checkin.

**Kelebihan**

* Dapat memenuhi kebutuhan reporting HR tanpa melakukan perubahan besar pada database utama aplikasi Checkin.
* Mengurangi scope perubahan pada aplikasi existing.
* Rumus perhitungan dapat diterapkan langsung pada modul report sesuai dengan kebutuhan HR.
* Data Step Out dan Step In dapat ditampilkan dalam bentuk rekap yang dibutuhkan untuk kebutuhan operasional dan audit.
* Mengurangi effort development dan risiko perubahan pada sistem Checkin yang sudah berjalan.
* Biaya development lebih rendah dibandingkan dengan melakukan perubahan besar pada database utama Checkin.
* Implementasi dapat dilakukan lebih cepat.

**Kekurangan**

* Proses perhitungan dilakukan ketika report dijalankan atau ditampilkan sehingga terdapat kemungkinan waktu loading report menjadi lebih lama, terutama apabila volume data yang diproses besar.
* Performa report perlu diperhatikan dan dioptimalkan apabila jumlah data semakin banyak.
* Logic perhitungan berada pada modul report sehingga perlu dipastikan konsistensi rumus apabila digunakan oleh report lain.
* Apabila kebutuhan reporting berkembang secara signifikan, pendekatan ini dapat membutuhkan optimasi atau perubahan arsitektur di masa depan.

***

#### Decision

**Option 2 – Perhitungan Dilakukan pada Modul Report**

Sistem akan mengimplementasikan perhitungan jam kerja dan rekap aktivitas Step Out dan Step In pada modul Report.

Modul report yang dikembangkan terdiri dari:

1. **Laporan Jam Kerja**
   * Menampilkan total jam kerja karyawan.
   * Menghitung durasi kerja berdasarkan data attendance.
   * Mengurangi durasi jam kerja berdasarkan aktivitas Step Out dan Step In sesuai dengan logic yang telah ditentukan.
   * Menyediakan informasi yang dibutuhkan untuk analisis jam kerja.
2. **Laporan Rekap Step Out dan Step In**
   * Menampilkan detail aktivitas Step Out dan Step In.
   * Menampilkan durasi aktivitas.
   * Menyediakan informasi aktivitas sebagai dokumentasi dan kebutuhan audit HR.

Perhitungan akan dilakukan pada saat report diproses atau ditampilkan, tanpa melakukan perubahan besar pada struktur database utama aplikasi Checkin.

***

#### Reasoning

Keputusan untuk menggunakan **Option 2** diambil dengan mempertimbangkan kebutuhan bisnis saat ini dan efisiensi biaya development.

Project Owner mengharapkan implementasi dengan biaya development yang lebih rendah. Oleh karena itu, perubahan besar pada database utama aplikasi Checkin tidak menjadi prioritas pada tahap ini.

Dengan menempatkan logic perhitungan pada modul Report, kebutuhan HR tetap dapat difasilitasi tanpa melakukan perubahan signifikan terhadap sistem Checkin yang sudah berjalan.

Pendekatan ini juga dapat mengurangi scope development, effort migrasi data, dan risiko terhadap fitur existing.

Namun, karena proses perhitungan dilakukan saat report dijalankan, performa report perlu diperhatikan. Apabila volume data meningkat secara signifikan, sistem perlu dilakukan evaluasi dan optimasi, seperti optimasi query, indexing, caching, atau mempertimbangkan penyimpanan data hasil perhitungan secara terpisah pada tahap pengembangan berikutnya.
