# ADR-003

#### Topic&#x20;

Struktur kolom dan Tampilan Report

#### **Masalah**

User (Tim HR) butuh laporan attendance otomatis yang mencakup seluruh aktivitas (Check In/Out/Step In/Out, UT/OT, Notes, koordinat lokasi), bisa difilter sesuai kebutuhan export, mendukung Step In/Out berkali-kali dalam sehari, dan tidak memerlukan perubahan besar pada database utama Checkin (demi efisiensi biaya).

#### **Decision**

* Menampilkan seluruh kolom **Notes** dari tiap aktivitas (Check In/Out/Step In/Out) di halaman Report agar data eksplisit dan mudah difilter&#x20;
* Perhitungan & rekap dilakukan **di modul Report saat ditampilkan** (Option 2), bukan mengubah struktur database utama Checkin&#x20;

#### **Reasoning**

&#x20;Seluruh keputusan di kelompok ini konsisten diarahkan untuk **meminimalkan biaya & effort development** — memanfaatkan data yang sudah ada di aplikasi Checkin, menghindari perubahan besar pada database utama, sambil tetap memenuhi kebutuhan HR akan laporan yang detail, eksplisit, dan bisa difilter/diexport sesuai kebutuhan.

#### Discussion History&#x20;

| MOM                                                                                                                                                      | Person      |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| [Penampilan Notes untuk Seluruh Aktivitas Attendance pada Report](discussion-history.md#penampilan-notes-untuk-seluruh-aktivitas-attendance-pada-report) | Aini, Alif  |
| [Implementasi Report untuk Project Checkin](discussion-history.md#implementasi-report-untuk-project-checkin)                                             | Aini, Alif  |

