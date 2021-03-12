---
title: "Android Standard"
description: "Android Code Standard 2021"
lead: "Android Code Standard 2021"
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  standard:
    parent: "android"
weight: 30
toc: true
---



## Standard

- Architecture
  - Design Pattern
  - Foldering/packaging
- Code style and features
- Documentation
- Security
- Naming class ui (widget) & resources
- Third party libraries

## Architecture

- Modular
  - Project Features splited by module/library as possible
  - Core module to support other module/project
- Architecture Components Android Jetpack
- Design Pattern MVVM

### Inside Core Library

- Network/ Connection configurations
- Base -> ViewModel, Activity, Fragment, Adapter, WebView, etc
- Utils & Extentions
- Widgets
- Analytics Repository (for log event)
- In app updates function

### Modular Project

{{< img src="diagrammodular.png" alt="Diagram modular Image" caption="<em>Diagram modular Image</em>" class="border-0" >}}

### Foldering/Packaging

Structure of foldering/packaging in module are like this

```Stucture
app (module name)
│─── di
│  │   ...
│─── model
│  │   NotifRequestModel
│  │   NotifResponseModel
│─── repository
│  │   ...
│─── service
│  │   ...
│─── ui
│  │   main
│  │  │   MainViewModel
│  │  │   MainFragment
│  │  │   MainActivity
│  │   notif
│  │  │   ...
│─── util
│  │   ...
```

| Package | Description |
|-----|-----|
| **di** | Is a subpackage for dependency injection |
| **model** | Is a subpackage for class models |
| **repository** | Is a subpackage for api or local repository, that have function to help view model retrive data |
| **service** | Is a subpackage for all background related service packages/classes |
| **ui** | Is a subpackage for all UI-related packages/classes including their own view model class |
| **util** | For used global helper functions in module |

## Code Style, Features

Code

- [Kotlin style guide](https://developer.android.com/kotlin/style-guide)

Documentation Code

- K-Doc format, and use dokka engine documentation
- Markdown

Features

- Deeplink
- Analytics

## Security

- Proguard
- SSL Pinning
- Integrate Keystore
- Env variable value (cred data : Global Properties)
- Root (firebase)

## Best Practice

- Single-Activity arch
- Use Navigation Component
- Using kotlin with reactive programming
- Min SDK 21
- Using Dependency Injection
- Assets svg
- Core GraphQL (replacing webservice)
- Core Webservice
- Theme & Styling
- Tablet Version
  - Separated apk mobile and tablet
  - Same core business logic
  - Same repository (splited by branch)
  - Only different on layout

### Don’t do it

- __Don’t use beta/ alpha__ library version (ex: compose)
- __Don’t use Kotlin synthetics__ (not longer supported), use view binding instead
- To handle nullable __don’t use !!__, using lateinit, ?., ?: or ?.let{ /*do something*/ } instead

## Naming UI View

Most commonly used naming Android UI View classes following format abbrevation_name like below.

| View Class | Abbrevation | Naming Sample |
|----|----|----|
| CoordinatorLayout | cdl | cdl_profile |
| ConstraintLayout | csl | csl_main_fragment |
| AppBarLayout | abl | abl_main |
| Button | btn | btn_checkout |
| EditText | et | et_username |
| ProgressBar | pb | pb_checkout |
| TextView | tv | tv_info_update |
| RadioButton | rb | rb_male |

## Naming Resource

### Layout
Recommendation of layout names are like this.

{{< img src="layoutnamesample.png" alt="Drawable names Image" caption="<em>Drawable names Image</em>" class="border-0" >}}

### Drawables
We use <WHAT>_<DESCRIPTION> for strings naming. <WHAT> is Button,Dialog,Divider,Icon, etc & description give any extra information.

{{< img src="drawablenamesample.png" alt="Drawable names Image" caption="<em>Drawable names Image</em>" class="border-0" >}}

### String

String names start with a prefix that identifies the section they belong to. We use ``<HOW>_<DESCRIPTION>`` for strings naming. ``<HOW>`` to indicate reason of the string will be used & ``description`` give any extra information.

For ex:

{{< img src="stringnamesample.png" alt="String names Image" caption="<em>String names Image</em>" class="border-0" >}}

* ``<string name="label_update_app_now">Update aplikasi sekarang!</string>`` : how = label & update_app_now is description of the string.
* ``<string name="hint_user_name">``Masukkan Username</string> : how = hint & user_name is the description of string.

## 3rd party libraries

- Jetpack Components
- navigation, paging, camera, fragment, livedata, room, etc
- Async : Coroutines
- Dependency Injection : Dagger2/ Koin
- Network/ Connection : Retrofit
- Unit Testing : JUnit + Mockito
- Load Image : Glide
- Others : From google first than commons used