**Liquid State**
---

The current state of the mug

* **UUID**

`fc540008-236c-4c94-8fa9-944a3e5353fa`

* **Methods**

`READ`

* **Data Format**

Size: 1 Byte

Observations: The device emits state `3` but it is not registered by the app, though recorded in its analytics.

This data is read after state change events to facilitate data collection through the app.


* **Example Data**

* 1 -> Empty
* 2 -> Filling
* 3 -> (Unknown)
* 4 -> Cooling
* 5 -> Heating
* 6 -> Stable Temperature

