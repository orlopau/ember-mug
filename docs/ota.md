**Over The Air**
---

Info about the current firmware running on the mug.

* **UUID**

`fc54000C-236c-4c94-8fa9-944a3e5353fa`

* **Methods**

`READ`

* **Data Format**

Size: 4-6 bytes

Byte | Data
---  | ---
0-1  | Firmware version UINT16 Little Endian
2-3  | Hardware version UINT16 Little Endian
4-5? | Bootloader version UINT16 Little Endian. Optional

* **Example Data**

`8A 01 0A 00`

`8A 01` -> firmware version `0x18A` (394)

`A` -> hardware version 10

Missing bootloader version defaults to 0