# Checkin

## Database&#x20;

<table><thead><tr><th>Nama Kolom (DB)</th><th width="163.60003662109375">Kolom Frontend</th><th>Type Data</th><th>Rules / Sample</th></tr></thead><tbody><tr><td>createdAt</td><td>Waktu Check-in</td><td>Date (ISO 8601)</td><td>Required. Diisi otomatis oleh sistem saat submit.<br>Sample: 2026-07-15T01:58:00Z</td></tr><tr><td>createdBy_id</td><td>ID User (tersembunyi, dari sesi login)</td><td>ObjectId</td><td>Required. Merujuk ke koleksi Users, diambil dari token/sesi login, bukan input manual.<br>Sample: 665f1a2b3c4d5e6f70810001</td></tr><tr><td>group_id</td><td>Group / Lokasi Kerja</td><td>ObjectId</td><td>Required. Merujuk ke koleksi Groups. Dipilih user dari dropdown atau default sesuai penugasan.<br>Sample: 665f1a2b3c4d5e6f70820001</td></tr><tr><td>photo</td><td>Foto Check-in</td><td>String (path/URL file)</td><td>Required. Hasil upload kamera (bukan galeri, sesuai ADR). Disimpan sebagai path storage.<br>Sample: Checkins/2026/07/15/userA_0658.jpg</td></tr><tr><td>lat</td><td>Latitude (dari GPS device)</td><td>Double</td><td>Required. Diambil otomatis dari GPS, read-only di UI.<br>Sample: -7.257472</td></tr><tr><td>lng</td><td>Longitude (dari GPS device)</td><td>Double</td><td>Required. Diambil otomatis dari GPS, read-only di UI.<br>Sample: 112.752090</td></tr><tr><td>address</td><td>Alamat (hasil reverse-geocoding)</td><td>String</td><td>Optional (lihat catatan schema: tidak ada di required[] meski deskripsi menyebut 'required').<br>Dikosongkan jika sinyal GPS lemah / reverse-geocode gagal.<br>Sample: Jl. Tunjungan No. 12, Surabaya, Jawa Timur</td></tr><tr><td>notes</td><td>Catatan Tambahan</td><td>String</td><td>Optional. Input bebas dari user (contoh: alasan telat, kondisi lapangan).<br>Sample: Kunjungan client, revisi jadwal</td></tr><tr><td>Type </td><td>Untuk menambahkan keterangan jenis absensi </td><td></td><td>Opsi yang tersedia : <br>Checkin, Checkout , stepin, step out</td></tr></tbody></table>

## Sample Database&#x20;

| No | Case / Employee                              | Type     | Date       | Days  | Time  | Lat       | Lng        | Notes                             |
| -- | -------------------------------------------- | -------- | ---------- | ----- | ----- | --------- | ---------- | --------------------------------- |
| 1  | Case 1 - Budi Santoso                        | Checkin  | 22/07/2026 | Rabu  | 08:00 | -7.28927  | 112.73471  | absen masuk                       |
| 2  | Case 1 - Budi Santoso                        | Checkout  | 22/07/2026 | Rabu  | 16:00 | -7.28912  | 112.73486  | pulang                            |
| 3  | Case 2 - Dewi Kartika                        | Checkin  | 22/07/2026 | Rabu  | 08:00 | -7.257472 | 112.75209  | absen masuk                       |
| 4  | Case 2 - Dewi Kartika                        | STEPOUT  | 22/07/2026 | Rabu  | 12:00 | -7.257322 | 112.75224  | makan siang                       |
| 5  | Case 2 - Dewi Kartika                        | STEPIN   | 22/07/2026 | Rabu  | 13:30 | -7.257172 | 112.75239  | kembali (1,5 jam)                 |
| 6  | Case 2 - Dewi Kartika                        | Checkout  | 22/07/2026 | Rabu  | 16:00 | -7.257022 | 112.75254  | pulang                            |
| 7  | Case 3 - Rina Wulandari                      | Checkin  | 22/07/2026 | Rabu  | 08:00 | -7.297    | 112.74     | absen masuk                       |
| 8  | Case 3 - Rina Wulandari                      | STEPOUT  | 22/07/2026 | Rabu  | 10:00 | -7.29685  | 112.74015  | istirahat                         |
| 9  | Case 3 - Rina Wulandari                      | STEPIN   | 22/07/2026 | Rabu  | 11:30 | -7.2967   | 112.7403   | kembali (1,5 jam)                 |
| 10 | Case 3 - Rina Wulandari                      | STEPOUT  | 22/07/2026 | Rabu  | 13:00 | -7.29655  | 112.74045  | antar dokumen ke client           |
| 11 | Case 3 - Rina Wulandari                      | STEPIN   | 22/07/2026 | Rabu  | 15:00 | -7.2964   | 112.7406   | kembali (2 jam tugas kantor)      |
| 12 | Case 3 - Rina Wulandari                      | Checkout  | 22/07/2026 | Rabu  | 16:00 | -7.29625  | 112.74075  | pulang                            |
| 13 | Case 4 - Yusuf Ibrahim                       | Checkin  | 22/07/2026 | Rabu  | 08:00 | -7.32     | 112.7      | absen masuk                       |
| 14 | Case 4 - Yusuf Ibrahim                       | STEPOUT  | 22/07/2026 | Rabu  | 10:00 | -7.31985  | 112.70015  | istirahat                         |
| 15 | Case 4 - Yusuf Ibrahim                       | STEPIN   | 22/07/2026 | Rabu  | 11:30 | -7.3197   | 112.7003   | kembali (1,5 jam)                 |
| 16 | Case 4 - Yusuf Ibrahim                       | STEPOUT  | 22/07/2026 | Rabu  | 13:00 | -7.31955  | 112.70045  | urus keperluan pribadi            |
| 17 | Case 4 - Yusuf Ibrahim                       | STEPIN   | 22/07/2026 | Rabu  | 15:00 | -7.3194   | 112.7006   | kembali (2 jam keperluan pribadi) |
| 18 | Case 4 - Yusuf Ibrahim                       | Checkout  | 22/07/2026 | Rabu  | 16:00 | -7.31925  | 112.70075  | pulang                            |
| 19 | Case 5 - Ahmad Fauzi (Sabtu, normal)         | Checkin  | 25/07/2026 | Sabtu | 08:00 | -7.257472 | 112.75209  | absen masuk - Sabtu               |
| 20 | Case 5 - Ahmad Fauzi (Sabtu, normal)         | Checkout  | 25/07/2026 | Sabtu | 13:00 | -7.257322 | 112.75224  | pulang - Sabtu, durasi 5 jam      |
| 21 | Case 6 - Siti Rahma (Sabtu, istirahat lebih) | Checkin  | 25/07/2026 | Sabtu | 08:00 | -7.446838 | 112.718933 | absen masuk - Sabtu               |
| 22 | Case 6 - Siti Rahma (Sabtu, istirahat lebih) | STEPOUT  | 25/07/2026 | Sabtu | 11:00 | -7.446688 | 112.719083 | istirahat                         |
| 23 | Case 6 - Siti Rahma (Sabtu, istirahat lebih) | STEPIN   | 25/07/2026 | Sabtu | 12:30 | -7.446538 | 112.719233 | kembali (1,5 jam)                 |
| 24 | Case 6 - Siti Rahma (Sabtu, istirahat lebih) | Checkout  | 25/07/2026 | Sabtu | 13:00 | -7.446388 | 112.719383 | pulang - Sabtu, durasi 5 jam      |
| 25 | Case 7 - Rina Wulandari (Senin)              | Checkin  | 27/07/2026 | Senin | 08:00 | -7.297    | 112.74     | absen masuk                       |
| 26 | Case 7 - Rina Wulandari (Senin)              | STEPOUT  | 27/07/2026 | Senin | 12:00 | -7.29685  | 112.74015  | istirahat                         |
| 27 | Case 7 - Rina Wulandari (Senin)              | STEPIN   | 27/07/2026 | Senin | 12:30 | -7.2967   | 112.7403   | kembali 30 menit                  |
| 28 | Case 7 - Rina Wulandari (Senin)              | Checkout  | 27/07/2026 | Senin | 16:00 | -7.29655  | 112.74045  | pulang                            |
