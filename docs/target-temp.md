**Target temperature**
---

Retrieves and sets the target temperature of the mug

* **UUID**

`fc540003-236c-4c94-8fa9-944a3e5353fa`

* **Methods**

`READ`
`WRITE`

* **Data Format**

Size: 2 Bytes
Type: UINT16 Little Endian

For calculating the real temperature in °C, multiply the value by 0.01.

Sending `0000` turns off the heater

* **Example Data**

For setting the mug temperature to 55.50 °C, send the UINT `5550`.