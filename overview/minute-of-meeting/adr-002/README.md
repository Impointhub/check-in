# ADR-002

#### Topic&#x20;

Mekanisme identifikasi jenis aktifitas (Chekin/Checkout/step-in/step-out)

#### Problem&#x20;

Sistem perlu cara untuk membedakan jenis aktivitas attendance (Check In, Check Out, Step In, Step Out) agar data bisa diolah otomatis jadi laporan, tanpa mengubah besar-besaran halaman/form utama Checkin.

#### **Decision :**&#x20;

Menggunakan **Button** (bukan Tag) sebagai mekanisme utama pencatatan jenis aktivitas — setiap aktivitas yang dilakukan lewat button dicatat langsung sesuai jenisnya, sehingga data lebih terarah dan proses query/report lebih cepat & scalable.

#### **Reasoning:**

Pendekatan Tag (keputusan awal) berpotensi memperlambat proses query/pembuatan laporan saat volume data besar. Button dipilih untuk meningkatkan performa report, menyederhanakan logic filtering, dan membuat sistem lebih scalable — meski berarti mengubah desain awal dan menambah effort development/testing

#### Discussion History&#x20;

| MOM                                                                                                                                                                                   | Person                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- |
| [Penambahan Kolom Tag untuk Aktivitas Check In, Check Out, Step In, dan Step Out](discussion-history.md#penambahan-kolom-tag-untuk-aktivitas-check-in-check-out-step-in-dan-step-out) | Aini, Alif              |
| [Penggunaan Button untuk Aktivitas Attendance](discussion-history.md#penggunaan-button-untuk-aktivitas-attendance)                                                                    | Aini, Alif, Bu kartika  |
