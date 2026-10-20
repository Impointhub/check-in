# Checkin

## CI.F1 - User redirect to login page

* Given user visit `/checkin/create` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

## CI.F2 - Display a text "camera permission blocked"

* Given I already logged in
* And I on the page `/checkin`
* And the camera permission status is Asking
* When I click button checkin

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And I click don't allow on the prompt

<figure><img src="../.gitbook/assets/image (156).png" alt=""><figcaption></figcaption></figure>

* Then I can view error message Camera access is blocked

<figure><img src="../.gitbook/assets/image (111).png" alt=""><figcaption></figcaption></figure>

## CI.F3 - Display a text "Location access is blocked"

* Given I already logged in
* And I on the page `/checkin`
* And the location permission status is asking
* When I click button checkin

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* When I click Don't Allow on the prompt

<figure><img src="../.gitbook/assets/image (157).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification Location access is blocked

<figure><img src="../.gitbook/assets/image (113).png" alt=""><figcaption></figcaption></figure>

## CI.F4 - Photo not captured. Please take a photo before continuing.

* Given I already logged in
* And I on the page `/checkin`
* And I have granted camera access permission
* When I click button checkin

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And I click submit button without take any photos

<figure><img src="../.gitbook/assets/image (107).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

* Then I can view notifications "photo not capture. please take a photo before continuing"

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

## CI.F5 - Location not found. Make sure GPS & internet are turned on, then try again

* Given I already logged in
* And I on the page `/checkin`
* and I have granted access permission for the camera
* and I did not grant GPS access permission
* When I click button checkin

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And I click capture

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

*   Then I can view notification "Location not found. Make sure GPS & internet are turned on, then try again"

    <figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

## CI.S1 - Checkin success, redirect to feed page

* Given I already logged in
* And I on the page `/checkin`
* And the camera permission status is Asking
* And the location permission status is asking
* When I click button checkin

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And I click allow on the camera prompt

<figure><img src="../.gitbook/assets/image (158).png" alt=""><figcaption></figcaption></figure>

* And I click allow on the location prompt

<figure><img src="../.gitbook/assets/image (159).png" alt=""><figcaption></figcaption></figure>

* And I click capture

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

* And I type absensi berhasil into column notes

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

* Then I can redirect to feedpage to see checkin data

{% hint style="info" %}
Note : Untuk tampilan feed absensi mengikuti tampilan app saat ini. _yang dirubah hanya tombol bawah._
{% endhint %}

* And I can see my check-in data with the following fields:

| Field     | Value                |
| --------- | -------------------- |
| Full Name | Nur Aini             |
| Username  | @nrainii             |
| Location  | 429812138, 239428323 |
| Notes     | Absensi berhasil     |
| Date      | 25 Jul 2026          |
| Time      | 08:00                |
| Photo     | Captured photo       |



<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

* And I can view button stepout, checkout, stepin in the bottom

<figure><img src="../.gitbook/assets/image (132).png" alt=""><figcaption></figcaption></figure>
