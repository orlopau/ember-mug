**Target temperature**
---

Retrieves and sets the current temperature of the mug

* **UUID**

`fc540002-236c-4c94-8fa9-944a3e5353fa`

* **Methods**

`READ`

* **Data Format**

Size: 2 Bytes
Type: UINT16 Little Endian

For calculating the real temperature in °C, multiply the value by 0.01.

* **Example Data**

When receiving `5550`, multiply by 0.01 to read the real temperature: 55.00 °C