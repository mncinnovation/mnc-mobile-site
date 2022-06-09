---
title: "IOS"
description: "MNCAppsSDK is a library to help you manage all MNC apps and make it easier to display and maintain in your application."
lead: "MNCAppsSDK is a library to help you manage all MNC apps and make it easier to display and maintain in your application."
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "mncapps"
weight: 34
toc: true
---


<p align="center">
<a href="https://cocoapods.org/pods/MNCAppsSDK"><img src="https://img.shields.io/cocoapods/v/MNCAppsSDK.svg?style=flat"></a>
<a href="https://cocoapods.org/pods/MNCAppsSDK"><img src="https://img.shields.io/cocoapods/p/MNCAppsSDK.svg?style=flat"></a>
</p>

## Features

### Dashboard Features

- [x] Manage apps.
- [x] Customize layout.
- [x] Customize apps order.
- [x] Manage click behavior.

### iOS SDK

- [x] Show all MNC apps.
- [x] Managed button click behavior.
- [x] Customize apps order.
- [x] Manage click behavior.
- [x] Objective-C support.
- [x] Swift support.

### How To Use

The simplest way to use it is you need to put all values (User Id, Bundle Id, etc.) into `MNCAppsRequest` and use it as parameter when present the `MNCAppsScreen` :

```swift
import MNCAppsSDK

let request = MNCAppsRequest()
request.setUserID("#YOUR_USER_ID")
request.setBundleid("#YOUR_BUNDLE_ID")
request.setLanguage("en") // "en" for english language and "id" for indonesia language
request.setIntervals(0) // how many days does the data need to be updated
        
let screen = MNCAppsScreen(request: request)
screen.setDarkMode(false)
screen.modalPresentationStyle = .fullScreen
self.present(screen, animated: false, completion: nil)
```

MNCAppsSDK will download all the MNC apps and store it in local device. Everytime Intervals value is zero (0), SDK will always redownload all the contents.
You can set Intervals value to set how many days you need to redownload all the contents. And whenever you don't had a network connection, SDK will display all stored contents from the latest download.

<p align="center">
<kbd><img src="https://i.postimg.cc/bYBp44Hm/light.png" alt="MNCAppsSDK-light" title="MNCAppsSDK-light" width="200"/></kbd>
<kbd><img src="https://i.postimg.cc/DwqWv7xv/dark.png" alt="MNCAppsSDK-dark" title="MNCAppsSDK-dark" width="200"/></kbd>
</p>

`MNCAppsScreen` is subclass from `UIViewController`. Beside `MNCAppsScreen`, there's `MNCAppsBody` which subclass of `UIView` and you can customize it size or customize the navigation bar.

```swift
let body = MNCAppsBody(frame: self.view.safeAreaLayoutGuide.layoutFrame, andRequest: request)
body.setDarkMode(false)
self.view.addSubview(body)
```

## Installation

For installation is recomended using Cocoapods.

### CocoaPods

```ruby
target 'MyApp' do
  pod 'MNCAppsSDK', '1.0.1'
end
```

### XCode Setup

For MNCAppsSDK version `1.0.1`, please set `Enable Bitcode` to `NO` in your Project's Build Setting.

And then, you need to add `LSApplicationQueriesSchemes` in your `.plist` file :

```
<key>LSApplicationQueriesSchemes</key>
<array>
<string>okezonecom</string>
<string>inewsapp</string>
<string>sindonews</string>
<string>thefthing</string>
</array> 
```

This `key` is needed to allow the application to open another app whenever user tap `Open` button inside your application.

Please note that value inside `LSApplicationQueriesSchemes` can be change or add sometimes depend of what changes in Dashboard. 
XCode will show inform you in console log about what you need to add inside `LSApplicationQueriesSchemes` so it can directly open the app.