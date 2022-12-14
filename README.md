# Ember Mug Bluetooth Documentation

## Introduction

This repository contains a reverse-engineered documentation for the bluetooth API of [Ember Mugs](https://ember.com/).

The information provided here was retrieved using the Ember smartphone app on Android using an **Ember Mug 2** and decompiling the APK through [Java decompilers](http://www.javadecompilers.com/apk).

It may not be applicable to other Ember mugs, but feel free to extend the documentation and open a pull request :).

## Privacy

Data collected by the bluetooth gets sent to: [`https://collector.embertech.com`](https://collector.embertech.com)

Read [Data Collection & Privacy](./data-collection.md) for more information.

## Documentation

All commands have a service UUID of `fc543622236c4c948fa9944a3e5353fa`

* [Mug color](./docs/mug-color.md)
* [Target temperature](./docs/target-temp.md)
* [Current temperature](./docs/current-temp.md)
* [Battery percentage](./docs/battery.md)
* [Temperature Unit](./docs/temperature-unit.md)
* [Liquid Level](./docs/liquid-level.md)
* [Liquid State](./docs/liquid-state.md)
* [Mug Name](./docs/mug-name.md)
* [Date & Timezone](./docs/time-date-zone.md)
* [Push events](./docs/push-events.md)
* [Firmware & Hardware Versions](./docs/push-events.md)


