---
title: "Flutter Standard"
description: "Flutter Code Standard 2021"
lead: "Flutter Code Standard 2021"
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  standard:
    parent: "flutter"
weight: 30
toc: true
---

## Goal

Other than MNC Code standard, flutter has more goal

- Standardize and unified way of code
- Beginner Friendly and flattening learning curve, since

## Standard

- Project Structure Standard
- Best Practice
- Security Standard
- Layout Standard
- Third Party Standard
- Documentation Standard

## Structure and Project Standard

The structure and design pattern are __inspired__ by __clean architecture__ and __MVC__, because those are then most common things that developers known.

### Structure

The structure of the project are like this

```Stucture
lib
│─── common
│  │   ...
│─── core
│  │   ...
│─── module
│  │   ...
│─── main.dart 
```

__Common__ used widget, utils, and model in every module.

__Core__ for global & application logic placed.

__Module__ for your every modules located

### Core

Developer have to define and implement

{{< img src="core-image.png" alt="Core Image" caption="<em>Core Structure</em>" class="border-0" >}}

| Folder   |      Definition  |
|----------|:-----------|
| App Version Manager |  App version manager are for app updater, to make sure the app have newest version |
| Assets |    Assets static file name   |
| Deeplink | Deeplink handler|
| Environment | Environment variable, constant manager, and security |
| Global Controller | Global Controller Manager|
| Base Network | Base Network of your project|
| Notification Handler | Notification Handler for your project |
| Route | Route Definition of your project |
| Style | Style definition for your project |

### Module

Place your ui and business logic in this folder, and it has this pattern

{{< img src="module-pattern.png" alt="Module Pattern" caption="<em>Module Pattern</em>" class="border-0" >}}

| Folder   |      Definition  |
|----------|:-----------|
| Controller |  The Controller module represents the logic of data flow within the application. It is the middle layer between the Repo and Screen layers. The Controller is responsible for updating the pipe when the data changes. |
| Data |    The Data module defines the IO logic of the application. This module must have a Repository the source data can be various and send data to Controller.   |
| Screen | The Screen module represents entry point of route and page of app. |
| Test | The Test module are place for current module unit, widget and integration test. |
| Widget | The Widget module are place for current module widgets. |

{{< img src="module.png" alt="Module" caption="<em>Module</em>" class="border-0" >}}

### Common

Common only contain model, widget, and utils

## Best practice

- Use __Flutter 2__
- Follow [Flutter Performance Best Practice](https://flutter.dev/docs/perf/rendering/best-practices)
- Follow [Dart Style](https://dart.dev/guides/language/effective-dart/style)
- Use __snake_case__ for every developer created file under lib folder, ex login_screen.dart, money_utils.dart, my_widget.dart
- Split Into 3 Environments __Staging, Beta, Production__
- Use __VSCODE__
- Use __Named Route__
- In model use PODO (Plain Old Dart Object) for easier maintainability
- Every function name in repository must have prefix __repo__, ex repoYourFunc()

## Security Standard

- Save Credential Token like JWT token in [Secure Storage](https://pub.dev/packages/flutter_secure_storage), not SQL, SharedPrefences, NSUserDefault
- Avoid print(somevar), use debugPrint or log
- Add Url validator in deeplink handler, avoid sql injection or such
- Ignore every credential file in git

## Layout Standard

- Use MaterialApp
- A Widget must in class, avoid function
- Make sure layout in width 300px are safe from widget overflow.
- Avoid large trees, split your code into small widgets instead. Max in a UI Layers has 500 lines
- Use Theme
- Use Color Theme first
- Avoid Hard Coded String in Text content

## Third Party Standard

1. There is no limitation for 3rd party UI Library make sure avaialable for flutter 2.
2. But if the library has OS functionality like bluetooth, camera etc. please use the library which created by google team, then most popular
3. Use these library for any mnc flutter project
    - State Management > GetX
    - Route Management > GetX
    - Dependency Management > GetX
    - Network > Dio
    - Firebase Crashlytic
    - Firebase Performance Monitoring
    - Firebase Analytic

## Documentation Standard

- Follow [Dart Documentation](https://dart.dev/guides/language/effective-dart/documentation)
- Add Method flow explanation for long method

## Resource

[Download Presentation](https://docs.google.com/presentation/d/1l-0TQTuK7GtiD9eQ8KssI948yl7JhFk7alq5YfxpF30/edit?usp=sharing)
