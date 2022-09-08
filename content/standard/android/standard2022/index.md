---
title: "Android Standard 2022"
description: "Android Code Standard 2022"
lead: "Android Code Standard 2022"
date: 2022-09-06T08:48:57+00:00
lastmod: 2022-09-06T08:48:57+00:00
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
  - Compose Architecture
- Code style and features
- Documentation
- Security
- Best Practice
- Naming Composable Widget & Resources
- Third party libraries

## Architecture

- Core Library
- Modular
  - Project Features splited by module/library as possible
  - Core module to support other module/project
- Architecture Components Android Jetpack
- Design Pattern MVVM

### Core Library

- Network/ Connection configurations
- Base -> ViewModel, Activity, Fragment, Adapter, WebView, etc
- Utils & Extentions
- Widgets
- Analytics Repository (for log event)
- In app updates function

Please check [Core Library Repo](https://github.com/mncinnovation/mnc-android-code-standard-core) for detail of how to use core library.

### Modular Project

{{< img src="diagrammodular.png" alt="Diagram modular Image" caption="<em>Diagram modular Image</em>" class="border-0" >}}

- **app** : main module project
- **module-1..module-N** : module of features. 
  To define module of feature, create a group of features. For example if we have a project like Gojek may the module are like below.
| Module Name | Description |
|-----|-----|
| auth | Module for authentication. In here there are login, register, forgot password |
| go-food | Module for GoFood. There are near me, voucher/ promo (go-food), history, etc. |
| go-send | Module for GoSend. There are within city, intercity and voucher |

- **common** : is a module to support other modules that have common used classes in project following their own contract/business model.
- **core** : core library.

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
│  │  │   MainScreen
│  │  │   MainContent
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

### Compose Architecture
{{< img src="compose_architecture.jpg" alt="Diagram modular Image" caption="<em>Architecture with Compose</em>" class="border-0" >}}

## Code Style, Features

Code

- [Kotlin style guide](https://developer.android.com/kotlin/style-guide)
- Using Jetpack Compose

Features

- Deeplink
- Analytics

## Documentation

- K-Doc format, and use dokka engine documentation
- Format Markdown

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
- Jetpack Compose
  - All of @Composable components should be able to use @Preview (use initial/mock data and no error when preview the widget)
  - State with ViewModel.
  - Place the state at ``StateHolder`` (use [State Hoisting way](https://developer.android.com/jetpack/compose/state#state-hoisting)).
  - Create reusable widget as possible (prevent redundant code).
- Setup [Android CI/CD](https://mobile.mncinnovation.id/blog/how-to-setup-android-ci/cd-in-mnc-repo/)

### Don’t do it

- __Don’t use beta/ alpha__ library version
- __Don’t use Kotlin synthetics__ (not longer supported), use view binding instead
- To handle nullable __don’t use !!__, using lateinit, ?., ?: or ?.let{ /*do something*/ } instead

## Naming Composable Widget Function

Most commonly used naming Android Composable function following format NameAbbrevation like below.

| Objective | Abbrevation | Naming Sample |
|----|----|----|
| Library Screen (State Holder) | Screen | LibraryScreen |
| Library Content | Content | LibraryContent |

## Naming Resource

### Drawables
We use <WHAT>_<DESCRIPTION> for strings naming. <WHAT> is Button,Dialog,Divider,Icon, etc & description give any extra information.

{{< img src="drawablenamesample.png" alt="Drawable names Image" caption="<em>Drawable names Image</em>" class="border-0" >}}

### String

String names start with a prefix that identifies the section they belong to. We use ``<HOW>_<DESCRIPTION>`` for strings naming. ``<HOW>`` to indicate reason of the string will be used & ``description`` give any extra information.

For ex:

{{< img src="stringnamesample.png" alt="String names Image" caption="<em>String names Image</em>" class="border-0" >}}

* ``<string name="label_update_app_now">Update aplikasi sekarang!</string>`` : how = label & update_app_now is description of the string.
* ``<string name="hint_user_name">``Masukkan Username</string> : how = hint & user_name is the description of string.

## Third party libraries

- Jetpack Components
- navigation, paging, camera, fragment, livedata, room, etc
- Async : Coroutines
- Dependency Injection : Dagger2/ Koin
- Network/ Connection : Retrofit
- Unit Testing : JUnit + Mockito
- Load Image : Glide
- Others : From google first than commons used