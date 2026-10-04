# Step in

## SI.F1 - User redirect to login page

* Given user visit `/checkin/create` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

## SI.F2 - Step In button disabled

* Given I already logged in&#x20;
* and I on the page `/checkin`
* and I dont have _step-out_ data
* then I will see the "Step In" button disabled.

<figure><img src="../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

## SI.F3 - Displaying a pop-up to request permission

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And the camera permission status is "Asking"
* and I have the step out data for the date corresponding to the step-in date.
* When I click button step in&#x20;

<figure><img src="../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the native browser permission prompt for the camera

<figure><img src="../.gitbook/assets/image (110).png" alt=""><figcaption></figcaption></figure>

* When I click \<Permission choice> on the prompt&#x20;

| Permission choice | Status\_Permission | Respon                        |
| ----------------- | ------------------ | ----------------------------- |
| Allow             | Allow              | Continue to next validation   |
| Don't Allow       | Blocked            | Camera access is blocked      |
| Dismiss           | Asking             | Re-validate permission status |

*   Then the camera permission status becomes \<Status\_Permission>

    * UI Status\_Permission "Blocked"



    <figure><img src="../.gitbook/assets/image (117).png" alt=""><figcaption></figcaption></figure>

    * UI Status\_Permission "Asking"



    <figure><img src="../.gitbook/assets/image (110).png" alt=""><figcaption></figcaption></figure>

## SI.F4 - Display a text "camera permission blocked

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And the camera permission status is "Blocked"
* and I have the step out data for the date corresponding to the step-in date.
* When I click button step in&#x20;

<figure><img src="../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

* Then I can view error message "Camera access is blocked"&#x20;

<figure><img src="../.gitbook/assets/image (117).png" alt=""><figcaption></figcaption></figure>

## SI.F5 - Displaying a pop-up to request permission

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And the location permission status is "asking"
* and I have the step out data for the date corresponding to the step-in date.
* When I click button step in&#x20;

<figure><img src="../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the native browser permission prompt for the location&#x20;

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

* When I click \<permission choice> on the prompt&#x20;

| Permission choice | Status\_Permission | Respon                        |
| ----------------- | ------------------ | ----------------------------- |
| Allow             | Allow              | Continue to next validation   |
| Don't Allow       | Blocked            | Location access is blocked    |
| Dismiss           | Asking             | Re-validate permission status |

*   Then the location camera permission status becomes \<status\_permission>&#x20;

    * UI Status\_Permission "Blocked"

    <figure><img src="../.gitbook/assets/image (116).png" alt=""><figcaption></figcaption></figure>

    * UI Status\_Permission "Asking"&#x20;



    <figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## SI.F6 - Display a text "Location not detected"

* Given I already logged in&#x20;
* And I on the page `/checkin`
* And the location permission status is "blocked"
* and I have the step out data for the date corresponding to the step-in date.
* When I click button step in&#x20;

<figure><img src="../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Location access is blocked"

<figure><img src="../.gitbook/assets/image (116).png" alt=""><figcaption></figcaption></figure>

SI.F7&#x20;\- Photo not captured. Please take a photo
---------------------

* Given I already logged in&#x20;
* And I on the page `/checkin`
* and I have the step out data for the date corresponding to the step-in date.
* I have granted camera access permission
* When I click button step in

<figure><img src="../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

* And I click submit button without take any photos

<figure><img src="../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

* Then I can view notifications "photo not capture. please take a photo before continuing"

<figure><img src="../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

SI.F8&#x20;\- Location not found.&#x20;Make sure GPS & internet&#x20;are turned on,&#x20;then try again
--------------------

* Given I already logged in&#x20;
* And I on the page `/checkin`
* and I have granted access permission for the camera
* and I did not grant GPS access permission
* and I have the step out data for the date corresponding to the step-in date.
* When I click button step in&#x20;

<figure><img src="../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

* And I click capture&#x20;

<figure><img src="../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

* And I click submit&#x20;

<figure><img src="../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Location not found. Make sure GPS & internet are turned on, then try again"

<figure><img src="../.gitbook/assets/image (64).png" alt=""><figcaption></figcaption></figure>

## SI.S1 - Step In success, redirect to feed page

* Given I already logged in&#x20;
* And I on the page `/checkin`
* and I have granted access permission for the camera
* and I have granted access GPS access permission
* and my location has been detected
* and I have the step out data for the date corresponding to the step-in date.
* When I click button step in

<figure><img src="../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

* And I click capture&#x20;

<figure><img src="../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

* And I type "step in dari bank untuk keperluan kantor" into column "notes"

<figure><img src="../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>

* And I  click submit&#x20;

<figure><img src="../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>

* Then I can redirect to feedpage&#x20;

{% hint style="info" %}
Note : Untuk tampilan feed absensi mengikuti tampilan app saat ini. _yang dirubah hanya tombol bawah._&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (68).png" alt=""><figcaption></figcaption></figure>
