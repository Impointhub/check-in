# Step out

## SO.F1 - User redirect to login page

* Given user visit `/checkin/create` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

## SO.F2 - See Button Checkin

* Given I already logged in
* and I on the page `/checkin`
* and I don't have the check-in data yet

<figure><img src="../.gitbook/assets/image (163).png" alt=""><figcaption></figcaption></figure>

* Then I will see the step out button disable&#x20;

<figure><img src="../.gitbook/assets/image (141).png" alt=""><figcaption></figcaption></figure>

## SO.F3 - Display a text "camera permission blocked"

* Given I already logged in
* And I on the page `/checkin`
* And the camera permission status is Asking
* and I have the checkin data for the date corresponding to the step out date.
* When I click button step out

<figure><img src="../.gitbook/assets/image (144).png" alt=""><figcaption></figcaption></figure>

* And I click Don't Allow on the prompt&#x20;

<figure><img src="../.gitbook/assets/image (164).png" alt=""><figcaption></figcaption></figure>

* Then I can view error message "Camera access is blocked"

<figure><img src="../.gitbook/assets/image (111).png" alt=""><figcaption></figcaption></figure>

## SO.F5 - Displaying a pop-up to request permission



<figure><img src="../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the native browser permission prompt for the location

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>



## SO.F6 - Display a text "Location access is blocked"

* Given I already logged in
* And I on the page `/checkin`
* And the location permission status is asking
* and I have the check-in data for the date corresponding to the step out date.
* When I click button step out

<figure><img src="../.gitbook/assets/image (145).png" alt=""><figcaption></figcaption></figure>

* And I click Dont Allow on the prompt&#x20;

<figure><img src="../.gitbook/assets/image (165).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Location access is blocked"

<figure><img src="../.gitbook/assets/image (116).png" alt=""><figcaption></figcaption></figure>

## SO.F7 - Photo not captured. Please take a photo before continuing

* Given I already logged in
* And I on the page `/checkin`
* and I have the check-in data for the date corresponding to the step out date.
* I have granted camera access permission
* When I click button step out

<figure><img src="../.gitbook/assets/image (146).png" alt=""><figcaption></figcaption></figure>

* And I click submit button without take any photos

<figure><img src="../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

* Then I can view notifications "photo not capture. please take a photo before continuing"

<figure><img src="../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

## SO.F8 - Location not found. Make sure GPS & internet are turned on, then try again

* Given I already logged in
* And I on the page `/checkin`
* and I have granted access permission for the camera
* and I did not grant GPS access permission
* and I have the check-in data for the date corresponding to the step out date.
* When I click button step out

<figure><img src="../.gitbook/assets/image (147).png" alt=""><figcaption></figcaption></figure>

* And I click capture

<figure><img src="../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

* And I type Ke bank untuk keperluan kantor into column notes

<figure><img src="../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Location not found. Make sure GPS & internet are turned on, then try again"

<figure><img src="../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

## SO.S1 - Step Out success, redirect to feed page

* Given I already logged in
* And I on the page `/checkin`
* And the camera permission status is Asking
* And the location permission status is asking
* and I have the check-in data for the date corresponding to the step out date.
* When I click button step out

<figure><img src="../.gitbook/assets/image (148).png" alt=""><figcaption></figcaption></figure>

* And I click Allow on the camera prompt&#x20;

<figure><img src="../.gitbook/assets/image (167).png" alt=""><figcaption></figcaption></figure>

* And I click Allow on the location prompt&#x20;

<figure><img src="../.gitbook/assets/image (168).png" alt=""><figcaption></figcaption></figure>

* And I click capture

<figure><img src="../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

* And I type Ke bank untuk keperluan kantor into column notes

<figure><img src="../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

* Then I can redirect to feedpage to see step out data

{% hint style="info" %}
Note : Untuk tampilan feed absensi mengikuti tampilan app saat ini. _yang dirubah hanya tombol bawah._
{% endhint %}

<figure><img src="../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

* Then, the step out duration will reduce working hours.
