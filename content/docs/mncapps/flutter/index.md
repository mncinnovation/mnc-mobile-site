---
title: "Flutter"
description: "This page you'll discover documentation about SDK and Library created by mobile team at MNC Innovation Center"
lead: "This page you'll discover documentation about SDK and Library created by mobile team at MNC Innovation Center"
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "mncapps"
weight: 33
toc: true
---


## Feature

Dashboard Feature

* Manage Apps
* Customize Layout
* Customize Apps Order
* Manage Click Behaviour

Flutter SDK

* Show All MNC Apps
* Managed Button Click Behaviour
* InApp WebView

**Available in Android, IOS.**

Test Status :

* Android ✅ Done

* iOS ✅ Done

## How To Use

This lib currently using material theme, if you flutter app using cuppertino app. it may break

### 1. Add dependency

    mncapps: ^2.0.0

### 2. Platform specific

#### iOS

add this to ios/runner/info.plist

    <key>LSApplicationQueriesSchemes</key>
    <array>
    <string>okezonecom</string>
    <string>inewsapp</string>
    <string>sindonews</string>
    <string>thefthing</string>
    </array>   
These lines added for check  if the app installed or not, and open it.
The Schemes may **change** or will be **added** more.

#### Android

Good to go, nothing to add.

### 3. Import it

    import  'package:mncapps/mncapps.dart';

### 4. Use it

#### Use the body

    child: MNCAppsBody(userID: 'Your UserID'),

#### Navigate to MNCApps Screen/Page

    Navigator.push(context,MaterialPageRoute( builder: (context)=>MNCAppsScreen(userID: 'Your UserID')));

#### Optionaly add cache to it

    MNCAppsBody(
        userID: "YOUR USER ID",
        cachingStrategy: CachingStrategy.Weekly,
      )
