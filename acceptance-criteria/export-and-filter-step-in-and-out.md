# Export & Filter Step In & Out

## E2.S1 - Export with filter, system displays report column according to filters

* Given I already logged in
* And I on the page `/checkin`
* When I click button O/I

<figure><img src="../.gitbook/assets/image (80).png" alt=""><figcaption></figcaption></figure>

* And I select filter period from 01/08/2026 and to 31/08/2026

<figure><img src="../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>

* And I select filter column Date, Day, Employee, Stepout, Stepin, Total

<figure><img src="../.gitbook/assets/image (136).png" alt=""><figcaption></figcaption></figure>

* And click export

<figure><img src="../.gitbook/assets/image (88).png" alt=""><figcaption></figcaption></figure>

* Then system can export for spesific column

<figure><img src="../.gitbook/assets/image (137).png" alt=""><figcaption></figcaption></figure>

## E2.S2 - Export without filter, system exports data for all columns

* Given I already logged in
* And I on the page `/checkin`
* When click button O/I

<figure><img src="../.gitbook/assets/image (93).png" alt=""><figcaption></figcaption></figure>

* And I click export

<figure><img src="../.gitbook/assets/image (85).png" alt=""><figcaption></figcaption></figure>

* Then I can export data from the beginning of the month up to today's date.

<figure><img src="../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

* And I can export data for all columns

<figure><img src="../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>
