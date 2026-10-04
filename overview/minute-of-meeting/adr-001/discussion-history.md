# Discussion History

## Implementasi Sistem Attendance Terintegrasi dan Pelaporan yang Siap untuk Audit

#### Topik&#x20;

Implementasi Sistem Attendance Terintegrasi dan Pelaporan yang Siap untuk Audit

#### Masalah

Organisasi membutuhkan solusi manajemen attendance yang dapat mencatat kehadiran dan aktivitas karyawan secara akurat selama jam kerja, sekaligus mendukung kebutuhan operasional dan audit.

Solusi yang dibutuhkan harus mampu:

* Memungkinkan user membuat dan mengelola group untuk mengorganisasi karyawan serta melakukan review data attendance secara kolektif.
* Mencatat aktivitas attendance karyawan, termasuk **Check In, Check Out, Step In, dan Step Out**.
* Mencatat aktivitas atau pergerakan karyawan selama jam kerja, seperti keperluan kantor, istirahat, atau keperluan lainnya, termasuk alasan aktivitas tersebut.
* Menghitung total jam kerja dan total durasi Step In dan Step Out, serta mendukung analisis **overtime** dan **undertime**.
* Mencatat informasi lokasi untuk seluruh aktivitas yang berkaitan dengan attendance guna mendukung proses validasi kehadiran dan audit.
* Menghasilkan laporan attendance yang dapat langsung digunakan untuk kebutuhan operasional dan HR tanpa memerlukan pengolahan data secara manual.
* Mendukung konfigurasi kolom laporan, termasuk kemampuan untuk menampilkan atau menyembunyikan informasi lokasi sesuai kebutuhan.
* Menyediakan proses attendance yang terstandarisasi melalui satu aplikasi yang dapat digunakan secara konsisten pada perangkat **iOS dan Android**.

#### Keputusan

Mengimplementasikan sistem attendance yang mendukung aktivitas **Check In, Check Out, Step In, dan Step Out**, termasuk validasi lokasi, deskripsi aktivitas, perhitungan jam kerja, serta pelaporan yang dapat dikonfigurasi.

#### Fitur

**1. Group Management**

* Memungkinkan user membuat dan mengelola group.
* Memungkinkan user menambahkan atau menetapkan anggota ke dalam group.
* Mendukung pelaporan dan analisis attendance berdasarkan group.

**2. Attendance Tracking**

* Mencatat aktivitas Check In dan Check Out.
* Mencatat aktivitas Step In dan Step Out.
* Mendukung pencatatan deskripsi atau alasan ketika karyawan melakukan Step Out, seperti keperluan kantor, istirahat, atau keperluan lainnya.

**3. Perhitungan Jam Kerja**

* Menghitung total jam kerja karyawan.
* Menghitung total durasi Step In dan Step Out.
* Mendukung perhitungan overtime dan undertime.

**4. Validasi Lokasi**

* Mencatat latitude dan longitude untuk seluruh aktivitas yang berkaitan dengan attendance.
* Mendukung validasi attendance berdasarkan informasi lokasi.
* Menyediakan data lokasi sebagai bagian dari kebutuhan audit.

**5. Reporting**

* Menghasilkan laporan attendance yang siap digunakan untuk kebutuhan HR dan operasional.
* Menampilkan data Check In, Check Out, Step In, dan Step Out.
* Menyediakan konfigurasi kolom laporan, termasuk opsi untuk menampilkan atau menyembunyikan informasi latitude dan longitude.
* Memungkinkan user membuat laporan attendance berdasarkan individu maupun group.

**6. Kompatibilitas Platform**

* Mendukung penggunaan aplikasi pada perangkat iOS dan Android dengan proses attendance yang terstandarisasi.

#### Alasan

Keputusan ini diambil dengan pertimbangan sebagai berikut:

* Data attendance harus dapat mendukung kebutuhan operasional sekaligus kebutuhan audit.
* Aktivitas karyawan yang terjadi selama jam kerja perlu dapat dilacak dan didokumentasikan dengan baik.
* Informasi lokasi diperlukan untuk membantu memvalidasi aktivitas attendance dan mendukung proses audit.
* Otomatisasi laporan dapat mengurangi pekerjaan administratif dan meningkatkan akurasi data laporan.
* Perhitungan jam kerja diperlukan untuk mendukung analisis overtime dan undertime.
* Penggunaan satu platform attendance dapat menyederhanakan proses operasional dan meningkatkan konsistensi penggunaan aplikasi di seluruh organisasi.
