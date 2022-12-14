**Liquid Level**
---

Retrieves the level of liquid present in the cup

* **UUID**

`fc540005-236c-4c94-8fa9-944a3e5353fa`

* **Methods**

`READ`

* **Data Format**

Size: 1 Byte

* **Observation**

This value only seems to update when the device is charging.

There may be values other intermediate values present but they have no significance for the app. Most likely because the liquid level sensor is too coarse to tell the difference.

* 0  -> Empty
* 30 -> Not Empty
