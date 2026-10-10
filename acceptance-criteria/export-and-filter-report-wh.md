# Export & Filter report WH

## E1.S1 - Export with filter, system displays check-in report column according to filters

* Given I already logged in
* And I on the page `/checkin`
* When I click wh

<figure><img src="../.gitbook/assets/image (131).png" alt=""><figcaption></figcaption></figure>

* And I select filter period from 01/08/2026 and to 08/08/2026

<figure><img src="../.gitbook/assets/image (94).png" alt=""><figcaption></figcaption></figure>

* And I select filter column attendance date, day, employee name, time in /clockin, time out / clock out, gross working duration, Step out duration, net workhour"

<figure><img src="../.gitbook/assets/image (123).png" alt=""><figcaption></figcaption></figure>

* And I click export

<figure><img src="../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

* Then the system can export workhour report according filter as excel format

{% hint style="info" %}
Format Excel : [https://docs.google.com/spreadsheets/d/1pK\_JPM9IdEwC2TiZIgbJEL8DIimu5M53niTEuM7i7LM/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1pK_JPM9IdEwC2TiZIgbJEL8DIimu5M53niTEuM7i7LM/edit?usp=sharing)
{% endhint %}

<figure><img src="../.gitbook/assets/image (128).png" alt=""><figcaption></figcaption></figure>

## E1.S2 - Export without filter, system exports data for all columns

* Given I already logged in
* And I on the page [https://checkin.pointhub.net/](https://checkin.pointhub.net/)
* When I click wh

<figure><img src="../.gitbook/assets/image (131).png" alt=""><figcaption></figcaption></figure>

* And I click export

<figure><img src="../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>

* Then I can export data from the beginning of the month up to today's date.

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

* And I can export data for all columns

<figure><img src="../.gitbook/assets/image (128).png" alt=""><figcaption></figcaption></figure>
