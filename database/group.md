# Group

## Database&#x20;

| Nama Kolom (DB) | Kolom Frontend          | Type Data         | Rules / Sample                                                                                                                                                                                                                                                                     |
| --------------- | ----------------------- | ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| createdAt       | Tanggal Dibuat          | Date (ISO 8601)   | <p>Required. Diisi otomatis oleh sistem saat group dibuat.<br>Catatan: description schema asli tertulis 'must be a string' padahal bsonType-nya 'date' — perlu diselaraskan.<br>Sample: 2026-07-10T02:30:00Z</p>                                                                   |
| createdBy\_id   | Dibuat oleh (Admin/PIC) | ObjectId          | <p>Required. Referensi ke koleksi Users. Diambil dari sesi login, bukan input manual.<br>Sample: 665f1a2b3c4d5e6f70810001</p>                                                                                                                                                      |
| name            | Nama Group/Lokasi       | String            | <p>Required. Min 3 karakter, maks 64 karakter.<br>Sample: Cabang Surabaya Pusat</p>                                                                                                                                                                                                |
| users           | Daftar Anggota Group    | Array of ObjectId | <p>Optional (tidak ada di required[]). Berisi referensi ke koleksi Users (anggota group).<br>Catatan: schema asli belum mendefinisikan items/bsonType elemen array — sebaiknya ditambahkan validasi 'items: { bsonType: objectId }'.<br>Sample: ["665f...0001", "665f...0002"]</p> |





## Sample Database&#x20;

| createdAt            | createdBy\_id            | name                  | users                                                                                                  |
| -------------------- | ------------------------ | --------------------- | ------------------------------------------------------------------------------------------------------ |
| 2026-07-10T02:30:00Z | 665f1a2b3c4d5e6f70810001 | Cabang Surabaya Pusat | 665f1a2b3c4d5e6f70810001, 665f1a2b3c4d5e6f70810002, 665f1a2b3c4d5e6f70810003                           |
| 2026-07-10T03:15:20Z | 665f1a2b3c4d5e6f70810001 | Cabang Sidoarjo       | 665f1a2b3c4d5e6f70810004, 665f1a2b3c4d5e6f70810005                                                     |
| 2026-07-11T06:05:11Z | 665f1a2b3c4d5e6f70810002 | Tim Lapangan Gresik   | 665f1a2b3c4d5e6f70810006                                                                               |
| 2026-07-12T01:40:00Z | 665f1a2b3c4d5e6f70810001 | Proyek Legacy 2024    |                                                                                                        |
| 2026-07-13T09:22:47Z | 665f1a2b3c4d5e6f70810003 | Divisi Finance HO     | 665f1a2b3c4d5e6f70810007, 665f1a2b3c4d5e6f70810008, 665f1a2b3c4d5e6f70810009, 665f1a2b3c4d5e6f70810010 |
