---
title: "Integrate a Flutter module into your Android project"
description: ""
lead: "Handle Incoming Intents from External Applications in Flutter"
date: 2021-04-22
lastmod: 2021-04-22
draft: false
weight: 50
images: ["android-from-flutter.png"]
contributors: ["Istiq Septiana"]
---

Flutter can handle incoming intents from Android by directly talking to the Android layer and requesting the data that was shared.
The basic flow implies that we first handle the shared text data on the Android native side (in our Activity), and then wait until Flutter requests for the data to provide it using a MethodChannel.

##### HOW TO USE IT (In Android)
Step 1: Add FlutterActivity to AndroidManifest.xml

```python
<activity
  android:name="io.flutter.embedding.android.FlutterActivity"
  android:theme="@style/LaunchTheme"
  android:configChanges="orientation|keyboardHidden|keyboard|screenSize|locale|layoutDirection|fontScale|screenLayout|density|uiMode"
  android:hardwareAccelerated="true"
  android:windowSoftInputMode="adjustResize"
  />
```
Step 2: Setup Flutter Engine

```python
private fun setupFlutterEngine() {
    flutterEngine = FlutterEngine(this)
    flutterEngine.dartExecutor.executeDartEntrypoint(DartExecutor.DartEntrypoint.createDefault())
    FlutterEngineCache.getInstance().put("flutter_engine", flutterEngine)
}
```

Step 3: Setup MethodChannel

```python
private fun setupMethodChannel() {
    MethodChannel(
        flutterEngine.dartExecutor.binaryMessenger, "com.innocent.audioresearch/audio"
        ).setMethodCallHandler { call, result ->
            when (call.method) {
                "getTitle" -> {
                    result.success("title" + call.argument<String>("audioTitle"))
                }
            }
        }
}
```

Step 4: Launch Flutter Activity and Send Data 

```python
button.setOnClickListener {
    setupFlutterEngine()
    setupMethodChannel()
    startActivity(
        FlutterActivity
        .withCachedEngine(FLUTTER_ENGINE_ID)
        .build(context))
}
```

##### HOW TO USE IT (In Flutter)

```python
@override
void initState() {
    super.initState();
    getAudioFromAndroid();
    sendDataTitleToAndroid();
}
```

```python
String _audioTitle = "No data";
getAudioFromAndroid() async {
    var title = await platform.invokeMethod('getTitle');
    if (title != null) {
      setState(() {
        _audioTitle = title;
      });
    }
}
```

```python
sendDataTitleToAndroid() async {
    SharedPreferences prefs = await SharedPreferences.getInstance();
    await platform.invokeMethod('getTitle', {"audioTitle": "title song"});
}
```

##### DEMO
Here’s an example of implementation.

###### List Data in Android
<img src="list-audio-android.png" width="250" />

###### Detail Data in Flutter (Data is obtained from list in android)
<img src="detail-audio-flutter.png" width="250" />

###### Send Data From Flutter to Android
<img src="android-from-flutter.png" width="250" />
