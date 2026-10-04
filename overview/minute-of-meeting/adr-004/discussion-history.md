# Discussion History

## Penambahan Workhour Schedule pada Master Group

#### Topic

Penambahan Workhour Schedule pada Master Group untuk Perhitungan Overtime dan Undertime

#### Problem / Background

Tim HC membutuhkan data **Overtime (OT)** dan **Undertime (UT)** pada laporan attendance untuk mendukung proses pengolahan dan analisis data absensi.

Untuk menghasilkan data tersebut, sistem perlu mengetahui standar atau target jam kerja yang harus dipenuhi oleh karyawan. Oleh karena itu, diperlukan parameter **Workhour Schedule** pada Master Group.

Rumus perhitungan **Workhour Real**:

> **Workhour Real = (Duration Check Out − Duration Check In) − (Duration Step Out − Duration Step In)**

Perhitungan Overtime dan Undertime dilakukan dengan membandingkan **Workhour Real** dengan **Workhour Schedule**:

* **Overtime (OT)**: Workhour Real > Workhour Schedule
* **Undertime (UT)**: Workhour Real < Workhour Schedule
* **Normal**: Workhour Real = Workhour Schedule



<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

#### Decision

Menambahkan field **Workhour Schedule** pada **Master Group** sebagai parameter standar jam kerja yang digunakan dalam perhitungan Overtime dan Undertime.

Nilai Workhour Schedule pada Group akan menjadi acuan sistem dalam menghitung dan menghasilkan data OT/UT pada laporan attendance.

#### Kelebihan

* Mempermudah sistem dalam menghasilkan data Overtime dan Undertime secara otomatis.
* Menyediakan parameter standar jam kerja sebagai dasar perhitungan attendance.
* Mengurangi kebutuhan pengolahan data absensi secara manual oleh tim HC.
* Mendukung konsistensi perhitungan OT dan UT berdasarkan Group.

#### Kekurangan

* Menambah requirement dan field baru pada Master Group.
* Membutuhkan penyesuaian database, UI, dan logic perhitungan.
* Perubahan Workhour Schedule pada Group dapat berdampak pada hasil perhitungan laporan attendance.

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

#### Reasoning

Penambahan **Workhour Schedule** dilakukan untuk mencapai measurable goal **"Mendukung efisiensi operasional HC, khususnya dalam pengolahan data absensi."**

Dengan menyediakan parameter jam kerja pada Master Group, sistem dapat menghitung Overtime dan Undertime secara otomatis sehingga mengurangi proses pengolahan data secara manual dan meningkatkan efisiensi proses administrasi HC



## Penanda Undertime/Overtime untuk User yang Tidak Melakukan Check Out

#### Topic

Penanda UT/OT ketika user melakukan Check In tetapi tidak melakukan Check Out

#### Problem / Background

Terdapat kondisi ketika user melakukan **Check In**, tetapi lupa melakukan **Check Out** pada akhir jam kerja.

Berdasarkan peraturan tata tertib perusahaan, apabila employee tidak melakukan Check In atau Check Out, maka employee dianggap **tidak masuk kerja**.

Diperlukan mekanisme penanda pada laporan agar kondisi tersebut dapat teridentifikasi dengan mudah oleh tim HR tanpa memerlukan proses pengecekan dan data cleaning secara manual.

#### Decision

Apabila user melakukan **Check In** tetapi tidak melakukan **Check Out**, maka sistem akan memberikan nilai **-8 jam** pada kolom **UT/OT** sebagai penanda bahwa data attendance dianggap tidak memenuhi ketentuan kehadiran.

Nilai **-8 jam** digunakan sebagai indikator khusus agar data dapat segera diidentifikasi dan ditindaklanjuti oleh tim HR.

#### Kelebihan

* Memudahkan tim HR mendeteksi user yang lupa melakukan Check Out.
* Mengurangi kebutuhan proses data cleaning secara manual.
* Mempercepat proses identifikasi data attendance yang tidak lengkap.
* Mendukung otomatisasi proses validasi data attendance.

#### Kekurangan

* Nilai **-8 jam** dapat terlihat seperti Undertime yang disebabkan oleh durasi Step In/Step Out apabila tidak terdapat penjelasan atau indikator khusus pada report.
* Membutuhkan dokumentasi atau penanda yang jelas agar nilai **-8 jam** tidak disalahinterpretasikan sebagai hasil perhitungan jam kerja normal.

#### Reasoning

Keputusan ini dibuat untuk mendukung **Smart Goal: Mengurangi risiko human error akibat proses data cleaning manual**.

Dengan memberikan penanda otomatis pada data attendance yang tidak lengkap, tim HR dapat lebih cepat mengidentifikasi dan menindaklanjuti kasus user yang lupa melakukan Check Out tanpa harus melakukan pengecekan data secara manual.



## Rumus untuk perhitungan under time dan overtime&#x20;

#### Topic

Rumus Perhitungan Undertime dan Overtime

#### Problem / Background

Saat ini, proses perhitungan **total jam kerja (work hour)** masih dilakukan secara manual dengan melakukan export data dari aplikasi **Pin Point** dan **Checkin**, kemudian data tersebut diolah untuk menentukan apakah karyawan mengalami **Undertime** atau **Overtime**.

Untuk mengotomatisasi proses tersebut, diperlukan rumus perhitungan yang dapat menentukan kondisi **Undertime** dan **Overtime** berdasarkan total jam kerja karyawan.

Terdapat ketentuan jam kerja yang berlaku untuk hari kerja **Senin–Jumat**, yaitu karyawan diwajibkan memenuhi minimal **7 jam kerja efektif per hari**.&#x20;

* Ketika hari senin - jum'at menggunakan minimal  7 jam kerja. Rumus untuk menentukan undertime / overtime pada hari kerja :&#x20;

| 1. WEEKDAY (Senin - Jumat)                                                                                             |
| ---------------------------------------------------------------------------------------------------------------------- |
| Net Working Hours = Span (Checkout - Checkin) - Break (1 jam) - Step out (Break + personal needs)                      |
| - Break: selalu 1 jam, dikurangi otomatis walau tanpa Step Out sama sekali.                                            |
| - Istirahat Excess: berlaku HANYA untuk Step Out berkategori 'Istirahat'.                                              |
| \* Jika durasi aktual < 1 jam -> dianggap 1 jam (diserap standard break, TIDAK ada potongan tambahan).                 |
| \* Jika durasi aktual >= 1 jam -> selisihnya (aktual - 1 jam) DIGABUNG ke Personal Deduction (bukan kategori sendiri). |
| - Personal Deduction = Istirahat Excess (jika ada) + Total Step Out kategori 'Keperluan Pribadi'. Dipotong PENUH.      |
| - Keperluan Kantor: TIDAK mengurangi jam kerja sama sekali (dianggap tetap bekerja).                                   |
| - Label: Net < 7 jam -> UT (Under Time) \| Net = 7 jam -> Normal \| Net > 7 jam -> OT (Overtime)                       |



* Ketika hari sabtu menggunakan minimal 5 jam kerja tanpa istirahat. Rumus untuk menentukan undertime / overtime pada hari kerja :&#x20;



| 2. SATURDAY (Sabtu)                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------- |
| Net Working Hours = Span (Checkout - Checkin) - Standard Break (0 jam) - Personal Deduction                         |
| - Standard Break: SELALU 0 jam (tidak ada istirahat formal, karena hari kerja hanya 5 jam).                         |
| - Kategori 'Istirahat' TIDAK BERLAKU di hari Sabtu -> opsi ini disembunyikan dari form Step Out saat hari Sabtu.    |
| - Jika karyawan step out untuk istirahat di hari Sabtu, WAJIB diisi sebagai 'Keperluan Pribadi', bukan 'Istirahat'. |
| - Personal Deduction = Total Step Out kategori 'Keperluan Pribadi'. Dipotong PENUH.                                 |
| - Keperluan Kantor: TIDAK mengurangi jam kerja sama sekali (sama seperti weekday).                                  |
| - Label: Net < 5 jam -> UT (Under Time) \| Net = 5 jam -> Normal \| Net > 5 jam -> OT (Overtime)                    |



*   Simulasi Kasus untuk perhitungan jam kerja&#x20;

    *   Workhour Report&#x20;

        <figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>
    * Step in - Step out&#x20;

    <figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>



#### Option

#### Option 1 – Minimal Jam Kerja Dikonfigurasi pada Group

Minimal jam kerja ditambahkan sebagai atribut atau konfigurasi pada **Group**.

Setiap Group dapat memiliki pengaturan minimal jam kerja yang berbeda sesuai dengan kebutuhan perusahaan atau kelompok karyawan.

Sebagai contoh:

* Group A → Minimal 7 jam kerja
* Group B → Minimal 8 jam kerja

**Kelebihan**

* Lebih fleksibel dalam menentukan minimal jam kerja.
* Dapat mendukung kebutuhan beberapa perusahaan atau kelompok dengan aturan jam kerja yang berbeda.
* Perubahan minimal jam kerja dapat dilakukan melalui konfigurasi Group tanpa memerlukan perubahan pada logic atau source code.
* Lebih scalable apabila ke depannya terdapat variasi aturan jam kerja berdasarkan Group.

**Kekurangan**

* Membutuhkan perubahan pada struktur database Group dengan menambahkan atribut atau field terkait minimal jam kerja.
* Membutuhkan perubahan pada UI untuk mengelola konfigurasi minimal jam kerja.
* Membutuhkan tambahan logic untuk membaca konfigurasi minimal jam kerja berdasarkan Group.
* Membutuhkan effort development dan testing yang lebih besar.
* Berpotensi meningkatkan kompleksitas pengelolaan Group apabila konfigurasi jam kerja semakin banyak.

***

#### Option 2 – Minimal Jam Kerja Didefinisikan pada Logic atau Rumus

Minimal jam kerja ditentukan secara langsung pada logic atau rumus perhitungan.

Untuk kebutuhan saat ini, minimal jam kerja ditetapkan sebesar **7 jam per hari untuk hari Senin–Jumat**.

Logic perhitungan akan menggunakan nilai tersebut sebagai parameter tetap dalam menentukan Undertime dan Overtime.

**Kelebihan**

* Tidak memerlukan perubahan struktur database Group.
* Tidak memerlukan penambahan konfigurasi pada halaman Group.
* Implementasi lebih sederhana dan cepat.
* Mengurangi effort development dibandingkan dengan penambahan konfigurasi yang bersifat dinamis.
* Biaya development lebih rendah karena perubahan hanya dilakukan pada logic perhitungan.
* Sesuai dengan kebutuhan saat ini karena laporan digunakan untuk kebutuhan internal HR.

**Kekurangan**

* Kurang fleksibel apabila setiap Group atau perusahaan memiliki aturan minimal jam kerja yang berbeda.
* Apabila terdapat perubahan aturan minimal jam kerja, diperlukan perubahan pada logic atau proses development kembali.
* Perubahan aturan membutuhkan proses deployment ulang.
* Kurang scalable untuk kebutuhan bisnis yang memiliki variasi aturan jam kerja di masa depan.

***

#### Decision

**Option 2 – Minimal Jam Kerja Didefinisikan pada Logic atau Rumus**

Untuk implementasi saat ini, minimal jam kerja akan ditentukan secara langsung pada logic perhitungan.

Ketentuan yang digunakan adalah:

> **Minimal jam kerja untuk hari Senin–Jumat adalah 7 jam kerja efektif per hari.**

Sistem akan menggunakan nilai tersebut untuk menghitung:

* **Undertime**, apabila total jam kerja efektif kurang dari 7 jam.
* **Overtime**, apabila total jam kerja efektif lebih dari 7 jam.
* Tidak terdapat Undertime maupun Overtime apabila total jam kerja efektif tepat 7 jam.

Perhitungan akan diterapkan pada laporan attendance yang digunakan oleh HR untuk kebutuhan internal.

***

#### Reasoning

Keputusan untuk menggunakan **Option 2** diambil karena kebutuhan laporan saat ini bersifat **custom untuk kebutuhan internal HR** dan belum membutuhkan konfigurasi minimal jam kerja yang dinamis berdasarkan Group.

Dengan menetapkan minimal jam kerja langsung pada logic atau rumus, implementasi dapat dilakukan dengan lebih sederhana dan membutuhkan effort development yang lebih rendah.

Pendekatan ini juga menghindari perubahan pada struktur database dan UI Group yang belum diperlukan untuk kebutuhan saat ini.

Apabila di masa depan terdapat kebutuhan untuk mendukung variasi jam kerja berdasarkan Group, perusahaan, hari kerja, atau shift, maka konfigurasi minimal jam kerja dapat dievaluasi kembali dan dipertimbangkan untuk dipindahkan menjadi **parameter yang dapat dikonfigurasi**.



## Perlakuan terhadap Data Lama

#### Topic

Perlakuan Logic terhadap Data Lama

#### Problem / Background

Terdapat perubahan dan penambahan rumus perhitungan pada sistem yang akan mulai diterapkan setelah proses development selesai.

Namun, aplikasi Checkin telah memiliki data historis yang tersimpan sebelum perubahan logic tersebut diterapkan. Oleh karena itu, perlu ditentukan bagaimana sistem akan memperlakukan data lama yang sudah tersedia.

Terdapat dua alternatif yang dipertimbangkan:

1. Melakukan update atau migrasi logic terhadap seluruh data lama yang sudah tersimpan.
2. Menerapkan rumus atau logic baru hanya untuk data yang dibuat setelah perubahan diimplementasikan.

Keputusan ini diperlukan untuk menentukan scope development dan memastikan konsistensi perhitungan antara data historis dan data baru.

***

#### Option

#### Option 1 – Update Logic untuk Seluruh Data Lama

Logic atau rumus baru diterapkan pada seluruh data yang sudah tersimpan di database, termasuk data historis sebelum perubahan dilakukan.

**Kelebihan**

* User tidak perlu melakukan perubahan atau penyesuaian data secara manual.
* Seluruh data menggunakan logic dan rumus perhitungan yang konsisten.
* Data historis dapat langsung mengikuti standar perhitungan yang baru.
* Mengurangi kebutuhan proses pemetaan atau penyesuaian data secara manual oleh tim HR.

**Kekurangan**

* Proses development menjadi lebih kompleks karena perlu menangani data historis.
* Membutuhkan proses migrasi atau data transformation terhadap data lama.
* Memerlukan validasi tambahan untuk memastikan hasil perhitungan data lama tetap akurat.
* Berpotensi memerlukan effort development dan testing yang lebih besar.
* Terdapat risiko perubahan hasil perhitungan pada data historis yang sebelumnya sudah digunakan sebagai referensi atau laporan.

***

#### Option 2 – Logic Baru Hanya Berlaku untuk Data ke Depan

Logic atau rumus baru hanya diterapkan pada data yang dibuat setelah perubahan sistem diimplementasikan.

Data historis yang sudah tersimpan sebelum perubahan tetap menggunakan logic atau perlakuan yang berlaku pada saat data tersebut dibuat.

**Kelebihan**

* Proses development lebih sederhana karena tidak memerlukan migrasi atau perubahan terhadap data historis.
* Mengurangi effort development dan testing.
* Mengurangi risiko perubahan terhadap data historis yang sudah digunakan sebagai referensi.
* Implementasi dapat dilakukan lebih cepat.
* Scope perubahan sistem menjadi lebih terkontrol.

**Kekurangan**

* Data lama dan data baru dapat menggunakan logic atau rumus perhitungan yang berbeda.
* Tim HR perlu melakukan pemetaan atau penyesuaian data lama secara manual apabila diperlukan.
* Laporan yang menggabungkan data lama dan data baru berpotensi memiliki perbedaan hasil perhitungan.
* Membutuhkan pemahaman yang jelas mengenai perbedaan logic antara data historis dan data baru.

***

#### Decision

**Option 2 – Logic Baru Hanya Berlaku untuk Data ke Depan**

Logic dan rumus perhitungan baru akan mulai diterapkan pada data yang dibuat setelah perubahan sistem diimplementasikan.

Data historis yang sudah tersedia sebelum perubahan tidak akan dilakukan update atau migrasi logic secara otomatis dan tetap mengikuti logic yang berlaku pada saat data tersebut dibuat.

Apabila diperlukan penyesuaian atau pemetaan terhadap data historis, proses tersebut akan dilakukan secara manual oleh tim HR sesuai dengan kebutuhan bisnis.

***

#### Reasoning

Keputusan untuk menggunakan **Option 2** diambil dengan pertimbangan untuk **menghemat budget dan effort development**.

Dengan menerapkan logic baru hanya pada data ke depan, tim development tidak perlu melakukan migrasi, transformasi, dan validasi ulang terhadap seluruh data historis yang sudah tersimpan.

Pendekatan ini juga dapat mengurangi kompleksitas development dan risiko perubahan terhadap data lama yang telah digunakan sebagai referensi atau kebutuhan pelaporan sebelumnya.

Dengan demikian, perubahan logic dapat diterapkan secara lebih terkontrol tanpa memberikan dampak langsung terhadap data historis yang sudah ada.

## Proses Step In dan Step Out

#### Topic :&#x20;

Proses Step In dan Step Out

#### Problem / Background :&#x20;

Pada desain awal, proses **Step In** dan **Step Out** memiliki beberapa kategori aktivitas, yaitu:

* Keperluan Kantor
* Istirahat
* Keperluan Pribadi

Diperlukan keputusan terkait apakah kategori tersebut tetap digunakan dalam proses **Step Out** atau proses **Step Out** dibuat lebih sederhana tanpa kategori.

Selain itu, proses keluar pada jam kerja untuk keperluan tertentu akan dilakukan melalui mekanisme **izin kepada HR** menggunakan **Hash Memo** sebagai media pengajuan dan dokumentasi izin.

***

#### Option

#### Option 1 – Step Out Menggunakan Beberapa Kategori

Proses **Step Out** memiliki beberapa kategori aktivitas, yaitu:

* Keperluan Kantor
* Istirahat
* Keperluan Pribadi

Setiap aktivitas Step Out akan dicatat berdasarkan kategori yang dipilih oleh user.

**Kelebihan:**

* Data aktivitas Step Out lebih terstruktur dan mudah diklasifikasikan.
* Memudahkan HR atau perusahaan dalam melakukan analisis terhadap alasan user melakukan Step Out.
* Dapat digunakan sebagai dasar pembuatan laporan berdasarkan kategori aktivitas.
* Memiliki informasi yang lebih detail terkait aktivitas user selama jam kerja.

**Kekurangan:**

* Menambah kompleksitas pada proses Step Out karena user harus memilih kategori.
* Berpotensi meningkatkan cognitive load dan waktu yang dibutuhkan user untuk melakukan Step Out.
* Membutuhkan pengembangan dan maintenance terhadap master atau logic kategori.
* Dapat menimbulkan perbedaan interpretasi dalam menentukan kategori yang sesuai.
* Tidak sepenuhnya mendukung fleksibilitas proses kerja apabila kebutuhan aktivitas user tidak sesuai dengan kategori yang tersedia.

***

#### Option 2&#x20;

Proses **Step Out** tidak menggunakan kategori aktivitas. Sistem hanya mencatat waktu **Step Out** dan **Step In**.

Durasi Step Out akan dihitung sebagai waktu di luar aktivitas kerja dan dapat digunakan dalam perhitungan total jam kerja.

Secara konsep:

_**Net Working Hours  = Total Checkin-Checkout  - Break - Excursion Duration**_

Apabila user perlu keluar pada jam kerja untuk keperluan yang membutuhkan izin, proses pengajuan izin dilakukan kepada **HR melalui Hash Memo**. Dengan demikian, sistem Check In/Check Out hanya berfokus pada pencatatan waktu, sedangkan informasi mengenai alasan dan persetujuan izin dikelola melalui Hash Memo.

**Kelebihan:**

* Proses Step Out menjadi lebih sederhana dan cepat bagi user.
* Mengurangi cognitive load karena user tidak perlu memilih kategori ketika melakukan Step Out.
* Sistem lebih fleksibel dan adaptif terhadap berbagai jenis aktivitas user.
* Mengurangi kompleksitas database dan logic aplikasi karena tidak memerlukan pengelolaan kategori Step Out.
* Pemisahan tanggung jawab sistem menjadi lebih jelas: sistem attendance mencatat waktu, sedangkan Hash Memo menangani proses pengajuan dan persetujuan izin.
* Informasi terkait izin tetap terdokumentasi melalui Hash Memo sehingga dapat digunakan sebagai referensi dan audit trail.
* Lebih mudah dikembangkan dan dipelihara dalam jangka panjang.

**Kekurangan:**

* Sistem attendance tidak dapat secara langsung mengidentifikasi alasan user melakukan Step Out.
* HR tidak dapat melakukan analisis aktivitas Step Out berdasarkan kategori secara langsung dari data attendance.
* Membutuhkan integrasi atau keterkaitan proses dengan Hash Memo apabila informasi izin perlu digunakan dalam proses validasi atau pelaporan.
* Terdapat potensi data Step Out yang tidak memiliki izin apabila user tidak mengajukan Hash Memo sesuai prosedur perusahaan.
* Apabila di masa depan dibutuhkan laporan berdasarkan jenis aktivitas Step Out, data historis dari sistem attendance tidak memiliki informasi kategori.

#### Decision

**Decision: Option 2 – Step Out Tanpa Kategori**

Proses **Step Out** akan dilakukan tanpa menggunakan kategori aktivitas. Sistem hanya mencatat waktu **Step Out** dan **Step In** yang kemudian digunakan untuk menghitung durasi waktu di luar aktivitas kerja.

Untuk aktivitas keluar pada jam kerja yang membutuhkan izin, user wajib melakukan pengajuan izin kepada **HR melalui Hash Memo**.

Dengan demikian, tanggung jawab sistem dibagi menjadi:

1. **Attendance / Check In-Out**
   * Mencatat waktu Step In.
   * Mencatat waktu Step Out.
   * Menghitung durasi Step Out.
   * Menghitung total jam kerja berdasarkan waktu aktual.
2. **Hash Memo**
   * Menjadi media pengajuan izin.
   * Menyimpan informasi dan alasan izin.
   * Menyediakan proses approval oleh HR.
   * Menjadi dokumentasi dan audit trail terkait izin keluar pada jam kerja.

#### Reasoning

Keputusan menggunakan **Option 2** dipilih karena lebih sesuai dengan budaya perusahaan yang mendukung nilai **adaptif**.

Dengan tidak membatasi aktivitas Step Out ke dalam kategori tertentu, user memiliki fleksibilitas dalam menjalankan aktivitasnya tanpa menambah proses administratif pada saat melakukan Step Out.

Selain itu, pemisahan antara pencatatan waktu pada sistem attendance dan pengelolaan izin melalui Hash Memo membuat proses sistem menjadi lebih sederhana, fleksibel, dan memiliki tanggung jawab yang lebih jelas.

Pendekatan ini juga menghindari ketergantungan sistem attendance terhadap kategori aktivitas yang dapat berubah seiring dengan kebutuhan bisnis perusahaan.
