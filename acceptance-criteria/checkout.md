# Checkout

## CO.F1 - User redirect to login page

* Given user visit `/checkin/create` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

## CO.F2 - Displaying a pop-up to request permission camera

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And I have checkin data for date 25 jul 2026
* And the camera permission status is "Asking"
* When I click button checkout&#x20;

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the native browser permission prompt for the camera

<figure><img src="../.gitbook/assets/image (110).png" alt=""><figcaption></figcaption></figure>

* When I click \<permission choice> on the prompt&#x20;

| Permission choice | Status\_Permission | Respon                        |
| ----------------- | ------------------ | ----------------------------- |
| Allow             | Allow              | Continue to next validation   |
| Don't Allow       | Blocked            | Camera access is blocked      |
| Dismiss           | Asking             | Re-validate permission status |

*   Then the camera permission status becomes \<status permission>

    * UI Status\_Permission "Blocked"



    <figure><img src="../.gitbook/assets/image (111).png" alt=""><figcaption></figcaption></figure>

    * UI Status\_Permission "Asking"



    <figure><img src="../.gitbook/assets/image (110).png" alt=""><figcaption></figcaption></figure>

CO.F3&#x20;\- Display a text "camera permission blocked"
---------------------------------------------------

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And the camera permission status is "Blocked"
* When I click button checkout&#x20;

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

* Then I can view error message "Camera access is blocked"&#x20;

<figure><img src="../.gitbook/assets/image (111).png" alt=""><figcaption></figcaption></figure>

## CO.F4 - Displaying a pop-up to request permission location

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And the location permission status is "asking"
* When I click button checkout&#x20;

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the native browser permission prompt for the location&#x20;

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

* When I click \<Permission choice> on the prompt&#x20;

| Permission choice | Status\_Permission | Respon                        |
| ----------------- | ------------------ | ----------------------------- |
| Allow             | Allow              | Continue to next validation   |
| Don't Allow       | Blocked            | location access is blocked    |
| Dismiss           | Asking             | Re-validate permission status |

*   Then the location permission status becomes \<Status\_Permission>

    * UI Status\_Permission "Blocked"



    <figure><img src="../.gitbook/assets/image (115).png" alt=""><figcaption></figcaption></figure>

    * UI Status\_Permission "Asking"



    <figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## CO.F5 - Display a text "Location access is blocked"

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And the location permission status is "blocked"
* When I click button checkout&#x20;

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Location access is blocked"

<figure><img src="../.gitbook/assets/image (115).png" alt=""><figcaption></figcaption></figure>

CO.F6&#x20;\- Photo not captured.&#x20;Please take a photo&#x20;before continuing
-----------------------

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And I have granted camera access permission
* And I have check-in data for the same date as the check-out
* When I click button checkout&#x20;

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

* And I click submit button without take any photos

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

* Then I can view notifications "photo not capture. please take a photo before continuing"

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

CO.F7&#x20;\- Location not found.&#x20;Make sure GPS & internet are turned on, then try again
------------------------------------------------------------

* Given I already logged in&#x20;
* And I on the page `/checkin`
* and I have granted access permission for the camera
* and I did not grant GPS access permission
* and I have check-in data for the same date as the check-out
* When I click button checkout

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

* And I click capture

<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

&#x20;

* And I click submit&#x20;

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Location not found. Make sure GPS & internet are turned on, then try again"

<figure><img src="../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

## CO.S1 - Checkout success, redirect to feed page

* Given I already logged in&#x20;
* And I on the page `/checkin`
* and I have granted access permission for the camera
* and I have granted access GPS access permission
* and my location has been detected
* and I have check-in data for the same date as the check-out
* When I click button checkout

<figure><img src="../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

* And I click capture&#x20;

<figure><img src="../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

* And I type "absen berhasil" into column "notes"

<figure><img src="../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

* And I  click submit&#x20;

<figure><img src="../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

* Then I can redirect to feedpage&#x20;

{% hint style="info" %}
Note : Untuk tampilan feed absensi mengikuti tampilan app saat ini. _yang dirubah hanya tombol bawah._&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

* And I can see button checkin&#x20;

<figure><img src="../.gitbook/assets/image (135).png" alt=""><figcaption></figcaption></figure>
