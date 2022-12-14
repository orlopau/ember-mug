**Current date and timezone**
---

A write-only sink for the mug to store the current date and timezone

* **UUID**

`fc540006-236c-4c94-8fa9-944a3e5353fa`

* **Methods**

`WRITE`

* **Data Format**

Size: 5 Bytes

Byte | Value
---  | ---
0-3  | Unix timestamp recorded by the app. UINT32 Little Endian
4    | Timezone offset (ex: GMT+03)

* **Example Data**

```
Date Time   TZ
----------- --
B9 F0 98 63 03
```


```js
// interpreting the data in Javascript
console.log(new Date(0x6398F0B9 * 1000))
```

