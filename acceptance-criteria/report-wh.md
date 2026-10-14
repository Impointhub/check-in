# Report WH

## R1.S1 - System shows workhour report

* Given I already logged in
* And I on the page `/checkin`
* And I already have attendance data as bellow [(link)](https://docs.google.com/spreadsheets/d/1pK_JPM9IdEwC2TiZIgbJEL8DIimu5M53niTEuM7i7LM/edit?gid=1557068411#gid=1557068411)
* When I click wh

<figure><img src="../.gitbook/assets/image (134).png" alt=""><figcaption></figcaption></figure>

* Then I can see report workhour following the formula

{% hint style="info" %}
Net Working Hours = Gross Working Duration - Step Out Duration
{% endhint %}

| Attendance Date | Day   | Employee                                     | Check In | Check Out | Gross Working duration | Step out Duration | Net Working Hours |
| --------------- | ----- | -------------------------------------------- | -------- | --------- | ---------------------- | ----------------- | ----------------- |
| 22/07/2026      | Rabu  | Case 1 - Budi Santoso                        | 08:00    |           | 0.00                   | 1.50              | -1.50             |
| 22/07/2026      | Rabu  | Case 2 - Dewi Kartika                        | 08:00    | 16:00     | 8.00                   | 1.50              | 6.50              |
| 22/07/2026      | Rabu  | Case 3 - Rina Wulandari                      | 08:00    | 16:00     | 8.00                   | 3.50              | 4.50              |
| 22/07/2026      | Rabu  | Case 4 - Yusuf Ibrahim                       | 08:00    | 16:00     | 8.00                   | 3.00              | 5.00              |
| 25/07/2026      | Sabtu | Case 5 - Ahmad Fauzi (Sabtu, normal)         | 08:00    | 13:00     | 5.00                   | 0.00              | 5.00              |
| 25/07/2026      | Sabtu | Case 6 - Siti Rahma (Sabtu, istirahat lebih) | 08:00    | 13:00     | 5.00                   | 1.50              | 3.50              |
| 27/07/2026      | Senin | Case 7 - Rina Wulandari (Senin)              | 08:00    | 16:00     | 8.00                   | 0.50              | 7.50              |

<figure><img src="../.gitbook/assets/image (93).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (95).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (96).png" alt=""><figcaption></figcaption></figure>
