**Battery percentage and other values**
---

Retrieves the battery percentage of the mug and other values.

* **UUID**

`fc540007-236c-4c94-8fa9-944a3e5353fa`

* **Methods**

`READ`

* **Data Format**

Size: 5 Bytes

Byte | Value
--- | ---
0 | Battery percentage (5 - 100. Not scaled to 0 - 255)
1 | Charging status. 1 for plugged in, 0 for unplugged
2-3 | Battery temperature as UINT16 Little Endian, encoded like the [other temperatures](./target-temp.md)
4 | (Legacy) Most likely battery voltage

* **Example Data**

When receiving `4f 00 1c 0c 00`:

`4f` -> 79%

`00` -> Not charging

`1c 0c` -> 3100 (which maybe is 31.00 °C, battery temperature). Discarded by app

`00` -> Battery Voltage. Not set by device and discarded by app

