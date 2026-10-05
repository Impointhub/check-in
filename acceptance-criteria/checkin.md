# Checkin

## CI.F1 - User redirect to login page

* Given user visit `/checkin/create` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

## CI.F2 - Displaying a pop-up to request permission camera

* Given I already logged In&#x20;
* And I on the page `/checkin`
* And the camera permission status is Asking
* When I click button checkin&#x20;

<figure><img src="../.gitbook/assets/image (109).png" alt=""><figcaption></figcaption></figure>

* And the camera permission status is Asking

<figure><img src="../.gitbook/assets/image (110).png" alt=""><figcaption></figcaption></figure>

* When I click \<permission choice> on the prompt&#x20;

| Permission choice | Status\_Permission | Respon                        |
| ----------------- | ------------------ | ----------------------------- |
| Allow             | Allow              | Continue to next validation   |
| Don't Allow       | Blocked            | Camera access is blocked      |
| Dismiss           | Asking             | Re-validate permission status |

*   Then the camera permission status becomes \<Status\_Permission>

    * UI Status\_Permission Blocked



    <figure><img src="../.gitbook/assets/image (111).png" alt=""><figcaption></figcaption></figure>

    * UI Status\_Permission Asking



    <figure><img src="../.gitbook/assets/image (110).png" alt=""><figcaption></figcaption></figure>

## CI.F3 - Display a text "camera permission blocked"

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And the camera permission status is Blocked
* When I click button checkin&#x20;

<figure><img src="../.gitbook/assets/image (109).png" alt=""><figcaption></figcaption></figure>

* Then I can view error message Camera access is blocked&#x20;

<figure><img src="../.gitbook/assets/image (111).png" alt=""><figcaption></figcaption></figure>

## CI.F4 - Displaying a pop-up to request permission location

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And the location permission status is asking
* When I click button checkin&#x20;

<figure><img src="../.gitbook/assets/image (109).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the native browser permission prompt for the location

<figure><img src="../.gitbook/assets/image (112).png" alt=""><figcaption></figcaption></figure>

* When I click \<permission choice> on the prompt&#x20;

| Permission choice | Status\_Permission | Respon                        |
| ----------------- | ------------------ | ----------------------------- |
| Allow             | Allow              | Continue to next validation   |
| Don't Allow       | Blocked            | location access is blocked    |
| Dismiss           | Asking             | Re-validate permission status |

*   Then the location permission status becomes Status\_Permission

    * UI Status\_ Permission Blocked



    <figure><img src="../.gitbook/assets/image (113).png" alt=""><figcaption></figcaption></figure>
* UI Status Permission  asking

<figure><img src="../.gitbook/assets/image (112).png" alt=""><figcaption></figcaption></figure>

## CI.F5 - Display a text "Location access is blocked"

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And the location permission status is blocked
* When I click button checkin&#x20;

<figure><img src="../.gitbook/assets/image (114).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification Location access is blocked

<figure><img src="../.gitbook/assets/image (113).png" alt=""><figcaption></figcaption></figure>

CI.F6&#x20;\- Photo not captured. Please take a photo before continuing.
-------------------------------------------------------------------

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And I have granted camera access permission
* When I click button checkin&#x20;

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

* And I click submit button without take any photos

<figure><img src="../.gitbook/assets/image (107).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

* Then I can view notifications "photo not capture. please take a photo before continuing"

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

CI.F7&#x20;\- Location not found. Make sure GPS & internet are turned on, then try again
-----------------------------------------------------------------------------------

* Given I already logged in&#x20;
* And I on the page `/checkin`
* and I have granted access permission for the camera
* and I did not grant GPS access permission
* When I click button checkin&#x20;

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And I click capture&#x20;

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

* And I click submit&#x20;

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

*   Then I can view notification "Location not found. Make sure GPS & internet are turned on, then try again"

    <figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

## CI.S1 - Checkin success, redirect to feed page

* Given I already logged in&#x20;
* And I on the page `/checkin`
* and I have granted access permission for the camera
* and I have granted access GPS access permission
* and my location has been detected
* When I click button checkin

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And I click capture&#x20;

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

* And I type absen berhasil into column notes

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

* And I  click submit&#x20;

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

* Then I can redirect to feedpage to see checkin data&#x20;

{% hint style="info" %}
Note : Untuk tampilan feed absensi mengikuti tampilan app saat ini. _yang dirubah hanya tombol bawah._&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (126).png" alt=""><figcaption></figcaption></figure>

* And I can view button stepout, checkout, stepin in the bottom&#x20;

<figure><img src="../.gitbook/assets/image (127).png" alt=""><figcaption></figcaption></figure>
