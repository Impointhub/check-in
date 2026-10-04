# ADR-001

#### Topic&#x20;

Fondasi / Payung Utama Sistem Attendance

#### **Masalah**&#x20;

Organisasi membutuhkan solusi manajemen attendance yang dapat mencatat kehadiran & aktivitas karyawan secara akurat selama jam kerja, sekaligus mendukung kebutuhan operasional dan audit — mencakup group management, pencatatan Check In/Out/Step In/Out, validasi lokasi, perhitungan jam kerja (termasuk overtime/undertime), pelaporan otomatis yang siap pakai, dan satu platform yang konsisten untuk iOS & Android.

#### **Decision**&#x20;

Mengimplementasikan sistem attendance yang mendukung aktivitas Check In, Check Out, Step In, dan Step Out, termasuk validasi lokasi, deskripsi aktivitas, perhitungan jam kerja, serta pelaporan yang dapat dikonfigurasi — dibangun di atas 6 pilar fitur: Group Management, Attendance Tracking, Perhitungan Jam Kerja, Validasi Lokasi, Reporting, dan Kompatibilitas Platform.

#### **Reasoning**

Data attendance harus mendukung kebutuhan operasional sekaligus audit; aktivitas karyawan selama jam kerja perlu terlacak dan terdokumentasi; lokasi diperlukan untuk validasi; otomatisasi laporan mengurangi effort administratif; perhitungan jam kerja diperlukan untuk analisis OT/UT; satu platform menyederhanakan adopsi di seluruh organisasi.

#### Discussion History&#x20;

| MOM                                                                                                                                                                                      | Person               |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| [Implementasi Sistem Attendance Terintegrasi dan Pelaporan yang Siap untuk Audit](discussion-history.md#implementasi-sistem-attendance-terintegrasi-dan-pelaporan-yang-siap-untuk-audit) | Martien, Alif, Aini  |
