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

0 | Battery percentage as UINT16 Little Endian
1 | When 1, the device is charging
2-3 | Maybe battery temperature as UINT16, encoded like the other temperatures
4 | - (not known)

Observation: While charging, the fourth bit is always 1 -> Here you can detect if the device is charging, 
because the last 2 byte are enough to encode 0-100 percent.

* **Example Data**

When receiving `4f-00-1c-0c-00`:

We see the fourth byte is 0 -> Device is not charging.

`4f` -> 79%
`1c-0c` -> 3100 (which maybe is 31.00 °C, battery temperature?)

<br></br>
When receiving `4f-01-1c-0c-00`:

We see the fourth byte is 1, therefore the device is charging.

`4f` -> 79%
`1c-0c` -> 3100 (which maybe is 31.00 °C, but is not the same temperature shown in the app, maybe its another sensor? Or battery temperature?)