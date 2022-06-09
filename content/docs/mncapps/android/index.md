---
title: "Android"
description: "This page you'll discover documentation about SDK and Library created by mobile team at MNC Innovation Center"
lead: "This page you'll discover documentation about SDK and Library created by mobile team at MNC Innovation Center"
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "mncapps"
weight: 32
toc: true
---


## Feature

Dashboard Feature

* Manage Apps
* Customize Layout
* Customize Apps Order
* Manage Click Behaviour

Android SDK

* Show All MNC Apps
* Managed Button Click Behaviour
* InApp WebView

## How To Use

### Add Dependency

Gradle

```java
allprojects {
  repositories {
    ...
    maven { url 'https://jitpack.io' }
  }
}

dependencies {
  implementation 'com.github.mncinnovation:mnc-moreappsdk-android:1.0.0'
}

or Maven
```xml
<repositories>
  <repository>
    <id>jitpack.io</id>
    <url>https://jitpack.io</url>
  </repository>
</repositories>

<dependency>
  <groupId>com.github.mncinnovation</groupId>
  <artifactId>mnc-moreappsdk-android</artifactId>
  <version>1.0.0</version>
</dependency>
```

### Implement on you code

Navigate to MNCApps Screen/Page

```java
button.setOnClickListener {
  val intent = Intent(this, MNCAppsActivity::class.java)
  intent.putExtra(Constant.userID, [USER_ID])
  intent.putExtra(Constant.packageName, [PACKAGE_NAME])
  intent.putExtra(Constant.platformType, [PLATFORM_TYPE])
  startActivity(intent)
}
```

or use in your Activity if you want to use the custom Toolbar

```java
button.setOnClickListener {
  val intent = Intent(this, YourTargetActivity::class.java)
  intent.putExtra(Constant.userID, [USER_ID])
  intent.putExtra(Constant.packageName, [PACKAGE_NAME])
  intent.putExtra(Constant.platformType, [PLATFORM_TYPE])
  startActivity(intent)
}
```

Then, use in YourTargetActivity.class

```java
MNCAppsActivity.showFragment(R.id.appsFrameLayout, this)
```

and add in activity_yourtarget.xml

```xml
<FrameLayout
    android:id="@+id/appsFrameLayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"/>
```
