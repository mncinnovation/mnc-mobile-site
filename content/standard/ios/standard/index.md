---
title: "IOS Standard"
description: "IOS Code Standard 2021"
lead: "IOS Code Standard 2021"
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  standard:
    parent: "ios"
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

{{< img src="diagrammodular.jpeg" alt="Diagram modular Image" caption="<em>Diagram modular Image</em>" class="border-0" >}}

### Foldering/Packaging

//TODO BAYU

## Code Style, Features

Code

- [Kotlin style guide](https://developer.android.com/kotlin/style-guide)

Documentation Code

- K-Doc - dokka
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

TODO// Bayu

## Naming Resource

TODO// Bayu

## 3rd party libraries

- Jetpack Components
- navigation, paging, camera, fragment, livedata, room, etc
- Async : Coroutines
- Dependency Injection : Dagger2/ Koin
- Network/ Connection : Retrofit
- Unit Testing : JUnit + Mockito
- Load Image : Glide
- Others : From google first than commons used