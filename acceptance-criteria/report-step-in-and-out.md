# Report Step In & Out

## R2.F1 - User redirect to login page

* Given user visit `/checkin/create` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

## R2.S1 - System shows step out - step in report

* Given I on the report
* And I on the page `/checkin`
* And I have data step out - step in as below&#x20;
* When I click "O/I"
* Then I can see data following the formula&#x20;
  * Total step in - step out = Step out - Step in&#x20;

| Tanggal    | Nama Employee  | Days  | Time Step Out | Time Step In | Total Step In - Step Out | Step Out Notes          | Step In Notes                     |
| ---------- | -------------- | ----- | ------------- | ------------ | ------------------------ | ----------------------- | --------------------------------- |
| 22/07/2026 | Dewi Kartika   | Rabu  | 12:00         | 13:30        | 1:50                     | makan siang             | kembali (1,5 jam)                 |
| 22/07/2026 | Rina Wulandari | Rabu  | 10:00         | 11:30        | 1:50                     | istirahat               | kembali (1,5 jam)                 |
| 22/07/2026 | Rina Wulandari | Rabu  | 13:00         | 15:00        | 2:00                     | antar dokumen ke client | kembali (2 jam tugas kantor)      |
| 22/07/2026 | Yusuf Ibrahim  | Rabu  | 10:00         | 11:30        | 1:50                     | istirahat               | kembali (1,5 jam)                 |
| 22/07/2026 | Yusuf Ibrahim  | Rabu  | 13:00         | 15:00        | 2:00                     | urus keperluan pribadi  | kembali (2 jam keperluan pribadi) |
| 25/07/2026 | Siti Rahma     | Sabtu | 11:00         | 12:30        | 1:50                     | istirahat               | kembali (1,5 jam)                 |
| 27/07/2026 | Rina Wulandari | Senin | 12:00         | 12:30        | 0:50                     | istirahat               | kembali 30 menit                  |



<figure><img src="../.gitbook/assets/image (103).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (104).png" alt=""><figcaption></figcaption></figure>
