# ADR-004

#### Topic&#x20;

Rumus Perhitungan Jam kerja&#x20;

#### **Masalah**

Tim HR butuh data total jam kerja otomatis pada laporan attendance — saat ini perhitungan jam kerja masih manual via export data dari Pin Point & Checkin. Diperlukan: rumus perhitungan yang jelas, penanganan kasus khusus saat user lupa Check Out.&#x20;

**Decision :**&#x20;

* Rumus Perhitungan jam kerja : Net Working Hours = Total Checkin Checkout  − Step out Duration&#x20;

#### **Reasoning**

Kebutuhan laporan saat ini bersifat custom untuk kebutuhan internal HR, dan pembuatan sistem harus mengikuti **prinsip adaptif** bagi perusahaan — sehingga rumus dibuat sesederhana mungkin (tanpa kategori/pembedaan alasan Step Out) mengikuti keputusan pada [MOM Proses Step in dan Step out ](discussion-history.md#proses-step-in-dan-step-out)

#### **Discusssion History**&#x20;

| MOM                                                                                                                                                                | Person                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------- |
| [Penambahan Workhour Schedule pada Master Group](discussion-history.md#penambahan-workhour-schedule-pada-master-group)                                             | Aini, Alif , Martien    |
| [Penanda Undertime/Overtime untuk User yang Tidak Melakukan Check Out](discussion-history.md#penanda-undertime-overtime-untuk-user-yang-tidak-melakukan-check-out) | Aini, Alif              |
| [Rumus untuk perhitungan under time dan overtime](discussion-history.md#rumus-untuk-perhitungan-under-time-dan-overtime)                                           | Aini, Alif              |
| [Perlakuan terhadap Data Lama](discussion-history.md#perlakuan-terhadap-data-lama)                                                                                 | Aini, Alif              |
| [Proses step in dan step out ](discussion-history.md#proses-step-in-dan-step-out)                                                                                  | Aini, Alif, Bu kartika  |
