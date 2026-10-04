# Export & Filter Step In & Out

## E2.S1 - Export with filter, system displays report column according to filters

* Given I already logged in&#x20;
* And I on the page `/checkin`
* When I click button O/I
* And I select  filter period from 01/08/2026 and to 08/08/2026

<figure><img src="../.gitbook/assets/image (100).png" alt=""><figcaption></figcaption></figure>

* And I select filter column Date, Day, Employee, Stepout, Stepin, Total

<figure><img src="../.gitbook/assets/image (136).png" alt=""><figcaption></figcaption></figure>

* And click export&#x20;

<figure><img src="../.gitbook/assets/image (88).png" alt=""><figcaption></figcaption></figure>

* Then system can export for spesific column&#x20;

<figure><img src="../.gitbook/assets/image (137).png" alt=""><figcaption></figcaption></figure>

## E2.S2 - Export without filter, system exports data for all columns

* Given I already logged in&#x20;
* And I on the page `/checkin`
* When click button O/I
* And I click export&#x20;

<figure><img src="../.gitbook/assets/image (85).png" alt=""><figcaption></figcaption></figure>

* Then  I can export data from the beginning of the month up to today's date.

<figure><img src="../.gitbook/assets/image (101).png" alt=""><figcaption></figcaption></figure>

* And I can export data for all columns

<figure><img src="../.gitbook/assets/image (102).png" alt=""><figcaption></figcaption></figure>
