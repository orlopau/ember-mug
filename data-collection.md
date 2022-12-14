# Data Collection & Privacy

The ember mug continuously collects data from your mug and your surroundings and sends it to https://collector.embertech.com for analytics regularly.

The collected data includes but is not limited to:
- Fine grained geolocation (your exact longitude and latitude)
- The temperature of your mug
- Whether you have liquid in your mug
- Your IP (as an inevitable consequence of data collection)
- How you logged into the app
- Your mug name
- Your preferred temperature unit
- Your mug presets
- The current date including timezone
- Your email
- Your mobile OS and version info
- Basically anything you can imagine collecting, ember app collects

These analytics events happen:
- Once every day
- When you fill your mug
- When you empty your mug
- When your mug starts charging
- When your mug leaves the charging plate


## Interesting decompiled snippets

The app at some point wanted to respect GDPR and opt out of data collection for european citizens.

```java
@Subscribe
public void onLiquidStateChanged(OnLiquidStateChanged onLiquidStateChanged) {
    if (!EmberApp.isEuropeUnionUser()) {
        collectAppData(...);
        sendNewDrinkEventToFirebase();
        pushDailyAppData(...);
    }
}
```

But probably figured it either has no users in Europe or a lot of money to spend on lawsuits.

```java
private void checkEuropeUnion() {
    EmberApp.setIsEuropeUnionUser(false);
}
```

Or maybe they moved GDPR compliance to 3rd party services by discarding analytics based on IP which kind of defeats the point of GDPR in the first place.



```java
for (Preset next : appStatisticsData.getPresets()) {
    JSONObject jSONObject2 = new JSONObject();
    jSONObject2.put("name", next.getBeverage());
    jSONObject2.put("temp", next.getTemperature());
    jSONArray.put(jSONObject2);
}
jSONObject.put("presets", jSONArray);
jSONObject.put("liquidLevel", Integer.toString(mugService.getLiquidLevel()));
jSONObject.put("hw", mugService.getHardwareVersion());
jSONObject.put("loginMethod", getAuthLoginMethod(authorizationDataStore));
jSONObject.put("mobileOSVersion", Build.VERSION.RELEASE);
jSONObject.put("latitude", getLatitude(str));
jSONObject.put("deviceType", getDeviceType(mugService));
jSONObject.put("currentTemperature", String.valueOf(Math.round(evaluateUnits(true, mugService))));
jSONObject.put("fw", mugService.getFirmwareVersion());
jSONObject.put("mugId", mugService.getId());
jSONObject.put("date", getCurrentTimeInIso8601());
jSONObject.put("targetTemperature", String.valueOf(Math.round(evaluateUnits(false, mugService))));
jSONObject.put("temperatureUnit", getTemperatureUnit(mugService));
jSONObject.put("longitude", getLongitude(str2));
jSONObject.put("liquidState", getLiquidState(mugService));
jSONObject.put(RemoteConfigConstants.RequestFieldKey.APP_VERSION, appUtils.getVersionName());
jSONObject.put("email", getAuthEmail(authorizationDataStore));
jSONObject.put("mobilePlatform", MOBILE_PLATFORM);
jSONObject.put("mobileDevice", Build.MANUFACTURER + Build.PRODUCT);
      ```