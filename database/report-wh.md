# Report WH

## Database&#x20;

<table><thead><tr><th>Column</th><th width="149">Frontend Column</th><th>Description</th><th>Formula</th><th>Sample Data</th></tr></thead><tbody><tr><td>Attendance Date </td><td>Attendance Date </td><td>Tanggal user absen <br><br>Data dari created at</td><td>-</td><td>22/07/2026</td></tr><tr><td>Day </td><td>Day </td><td>Hari user absen <br><br>Data dari kolom createdy at</td><td>-</td><td>Rabu</td></tr><tr><td>Employee Name </td><td>Employee Name</td><td>user yang melakukan absen<br><br>Data dari kolom created by </td><td>-</td><td>Case 1 - Budi Santoso</td></tr><tr><td>Time in / Clock In  </td><td>Time in / Clock In  </td><td>Jam user melakukan absen checkin <br><br>Data dari kolom created at <br></td><td>-</td><td>08:00</td></tr><tr><td>Time out / Clock out </td><td>Time out / Clock out </td><td>Jam user  user melakukan absen checkout<br><br>Data dari kolom created at </td><td>-</td><td>16:00</td></tr><tr><td>Gross working duration </td><td>Gross working duration </td><td>Durasi user kerja  dalam satuan jam <br>contoh: <br>1.50 atau 1 jam 30 menit </td><td>Time out / clock out - Time in / clock in </td><td>8.00</td></tr><tr><td>Step Out Duration </td><td>Step Out Duration </td><td>Total user Step out - in. <br>durasi user dalam satuan jam (1.50 atau 1 jam 30 menit)</td><td><ul><li>Diperoleh dari total durasi step out dan step in </li></ul></td><td>0</td></tr><tr><td>Net Working hours</td><td>Net Working hours</td><td>Total jam kerja bersih user .<br>durasi user dalam satuan jam (1.50 atau 1 jam 30 menit)</td><td>Gross Working Duration - Step Out Duration</td><td>7.00</td></tr></tbody></table>

## Sample Database&#x20;

| Attendance Date | Day   | Employee                                     | Clock In |  Clock Out | Gross Working duration | Step out Duration | Net Working Hours |
| --------------- | ----- | -------------------------------------------- | ------------------ | -------------------- | ---------------------- | ----------------- | ----------------- |
| 22/07/2026      | Rabu  | Case 1 - Budi Santoso                        | 08:00              | 16:00                | 8.00                   | 0.00              | 8.00              |
| 22/07/2026      | Rabu  | Case 2 - Dewi Kartika                        | 08:00              | 16:00                | 8.00                   | 1.50              | 6.50              |
| 22/07/2026      | Rabu  | Case 3 - Rina Wulandari                      | 08:00              | 16:00                | 8.00                   | 3.50              | 4.50              |
| 22/07/2026      | Rabu  | Case 4 - Yusuf Ibrahim                       | 08:00              | 16:00                | 8.00                   | 3.50              | 4.50              |
| 25/07/2026      | Sabtu | Case 5 - Ahmad Fauzi (Sabtu, normal)         | 08:00              | 13:00                | 5.00                   | 0.00              | 5.00              |
| 25/07/2026      | Sabtu | Case 6 - Siti Rahma (Sabtu, istirahat lebih) | 08:00              | 13:00                | 5.00                   | 1.50              | 3.50              |
| 27/07/2026      | Senin | Case 7 - Rina Wulandari (Senin)              | 08:00              | 16:00                | 8.00                   | 0.50              | 7.50              |

