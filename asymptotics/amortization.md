# Amortization

{% hint style="warning" %}
This page is from my original notes and is not up to the latest quality standards. Read with care or [help make it better!](https://github.com/64bitpandas/cs61b-notes/pulls)
{% endhint %}

**Definition of Amortization:** "Spreading out"

* Getting the average cost for each operation from 1 to N
* Good analysis for when most actions have low cost but a few have very high cost
  * Example: Resizing arrays by doubling costs a lot of time/space every 2^nth action, but costs no extra space for every other action

**Potential**

* Using a generalized operation \(e.g. adding a constant\) to demonstrate amortized costs
* If \(actual - potential\) + \(previous differential\) &gt;= 0 for all operations, the amortized function is valid
