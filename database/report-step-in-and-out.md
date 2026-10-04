# Report Step In & Out

## Database&#x20;

<table><thead><tr><th>Column</th><th>Frontend Column</th><th>Description</th><th width="149">Formula</th><th>Sample Data</th></tr></thead><tbody><tr><td>Date </td><td>Date </td><td>Tanggal user absen <br><br>Data dari created at</td><td>-</td><td>22/07/2026</td></tr><tr><td>Day </td><td>Day </td><td>Hari user absen <br><br>Data dari kolom createdy at</td><td>-</td><td>Rabu</td></tr><tr><td>Employee Name </td><td>Employee Name</td><td>user yang melakukan absen<br><br>Data dari kolom created by </td><td>-</td><td>Case 2 - Dewi Kartika</td></tr><tr><td>Step Out </td><td>Step Out </td><td>Jam user melakukan absen step out <br><br>Data dari kolom created at <br></td><td>-</td><td>12:00</td></tr><tr><td>Step in </td><td>Step in </td><td>Jam user  user melakukan absen step in<br><br>Data dari kolom created at </td><td>-</td><td>13:30</td></tr><tr><td>Total Step in - Out </td><td>Total Step in - Out </td><td>Durasi user step in - step out </td><td>Step in - Step out </td><td>1.5</td></tr><tr><td>Step in notes </td><td>Step in notes </td><td>notes step in. diperoleh dari kolom notes </td><td>-</td><td>makan siang</td></tr><tr><td>Step Out Notes </td><td>Step Out Notes </td><td>notes step out. diperoleh dari kolom notes  </td><td>-</td><td>Makan siang</td></tr></tbody></table>

## Sample Database&#x20;

| Tanggal    | Nama Employee  | Days  | Time Step Out | Time Step In | Total Step In - Step Out | Step Out Notes          | Step In Notes                     |
| ---------- | -------------- | ----- | ------------- | ------------ | ------------------------ | ----------------------- | --------------------------------- |
| 22/07/2026 | Dewi Kartika   | Rabu  | 12:00         | 13:30        | 1:50                     | makan siang             | kembali (1,5 jam)                 |
| 22/07/2026 | Rina Wulandari | Rabu  | 10:00         | 11:30        | 1:50                     | istirahat               | kembali (1,5 jam)                 |
| 22/07/2026 | Rina Wulandari | Rabu  | 13:00         | 15:00        | 2:00                     | antar dokumen ke client | kembali (2 jam tugas kantor)      |
| 22/07/2026 | Yusuf Ibrahim  | Rabu  | 10:00         | 11:30        | 1:50                     | istirahat               | kembali (1,5 jam)                 |
| 22/07/2026 | Yusuf Ibrahim  | Rabu  | 13:00         | 15:00        | 2:00                     | urus keperluan pribadi  | kembali (2 jam keperluan pribadi) |
| 25/07/2026 | Siti Rahma     | Sabtu | 11:00         | 12:30        | 1:50                     | istirahat               | kembali (1,5 jam)                 |
| 27/07/2026 | Rina Wulandari | Senin | 12:00         | 12:30        | 0:50                     | istirahat               | kembali 30 menit                  |

