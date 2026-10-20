# Step in

## SI.F1 - User redirect to login page

* Given user visit `/checkin/create` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

## SI.F2 - Step In button disabled

* Given I already logged in
* and I on the page `/checkin`
* and I dont have stepout data
* then I will see the Step In button disabled.

<figure><img src="../.gitbook/assets/image (149).png" alt=""><figcaption></figcaption></figure>

## SI.F3 - Display a text "camera permission blocked

* Given I already logged in
* And I on the page `/checkin`
* And the camera permission status is Asking
* and I have the step out data for the date corresponding to the step-in date.
* When I click button step in

<figure><img src="../.gitbook/assets/image (150).png" alt=""><figcaption></figcaption></figure>

* And I click Don't Allow on the prompt

<figure><img src="../.gitbook/assets/image (169).png" alt=""><figcaption></figcaption></figure>

* Then I can view error message "Camera access is blocked"

<figure><img src="../.gitbook/assets/image (117).png" alt=""><figcaption></figcaption></figure>

## SI.F4 - Display a text "Location not detected"

* Given I already logged in
* And I on the page `/checkin`
* And the location permission status is asking
* and I have the step out data for the date corresponding to the step-in date.
* When I click button step in

<figure><img src="../.gitbook/assets/image (150).png" alt=""><figcaption></figcaption></figure>

* And I click Dont allow on the prompt

<figure><img src="../.gitbook/assets/image (170).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Location access is blocked"

<figure><img src="../.gitbook/assets/image (116).png" alt=""><figcaption></figcaption></figure>

## SI.F5 - Photo not captured . Please take a photo

* Given I already logged in
* And I on the page `/checkin`
* and I have the step out data for the date corresponding to the step-in date.
* I have granted camera access permission
* When I click button step in

<figure><img src="../.gitbook/assets/image (150).png" alt=""><figcaption></figcaption></figure>

* And I click submit button without take any photos

<figure><img src="../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

* Then I can view notifications "photo not capture. please take a photo before continuing"

<figure><img src="../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

## SI.F6 - Location not found. Make sure GPS & internet are turned on, then try again

* Given I already logged in
* And I on the page `/checkin`
* and I have granted access permission for the camera
* and I did not grant GPS access permission
* and I have the step out data for the date corresponding to the step-in date.
* When I click button step in

<figure><img src="../.gitbook/assets/image (150).png" alt=""><figcaption></figcaption></figure>

* And I click capture

<figure><img src="../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Location not found. Make sure GPS & internet are turned on, then try again"

<figure><img src="../.gitbook/assets/image (64).png" alt=""><figcaption></figcaption></figure>

## SI.S1 - Step In success, redirect to feed page

* Given I already logged in
* And I on the page `/checkin`
* And the camera permission status is Asking
* And the location permission status is asking
* and I have the step out data for the date corresponding to the step-in date.
* When I click button step in

<figure><img src="../.gitbook/assets/image (150).png" alt=""><figcaption></figcaption></figure>

* And I click Allow on the camera prompt

<figure><img src="../.gitbook/assets/image (171).png" alt=""><figcaption></figcaption></figure>

* And I click Allow on the location prompt

<figure><img src="../.gitbook/assets/image (172).png" alt=""><figcaption></figcaption></figure>

* And I click capture

<figure><img src="../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

* And I type step in dari bank untuk keperluan kantor into column notes

<figure><img src="../.gitbook/assets/image (65).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>

* Then I can redirect to feedpage to see step in data

{% hint style="info" %}
Note : Untuk tampilan feed absensi mengikuti tampilan app saat ini. _yang dirubah hanya tombol bawah._
{% endhint %}

* And I can see my step in data with the following fields

| Field     | Value                                     |
| --------- | ----------------------------------------- |
| Full Name | Nur Aini                                  |
| Username  | @nrainii                                  |
| Location  | -7.28632.112.73491                        |
| Notes     | Step in dari bank untuk keperluan kantor  |
| Date      | 25 Jul 2026                               |
| Time      | 15:05                                     |
| Photo     | Captured photo                            |

<figure><img src="../.gitbook/assets/image (80).png" alt=""><figcaption></figcaption></figure>
