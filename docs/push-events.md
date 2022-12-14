**Push Events**
---

Events sent by the mug for the application to register to.

* **UUID**

`fc540012-236c-4c94-8fa9-944a3e5353fa`

* **Methods**

`READ`
`NOTIFICATION`

* **Data Format**

Size: 1 Byte

These are notifications from the mug used to send events and also prompt the app to refresh certain stats by re-reading characteristics and/or sending metrics information.

States:

* 0x01 -> Refresh [battery level](./battery.md)
* 0x02 -> Charging
* 0x03 -> Not Charging
* 0x04 -> Refresh [target temperature](./target-temp.md)
* 0x05 -> Refresh [drink temperature](./current-temp.md)
* 0x06 -> _Not implemented_
* 0x07 -> Refresh [liquid level](./liquid-level.md)
* 0x08 -> Refresh [liquid state](./liquid-state.md)

