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

- Design Pattern
- Layout
- Folder
- Security
- Documentation
- Best Practice
- Review Code
- Must Have Features
- Third Party
- Optional Third Party

## Design Pattern

Model View ViewModel + RXSwift

## Layout

- XIB File + Snapkit, Specific for 1 view

## Folder

{{< img src="ioscorefolder.png" alt="Core folder Image" caption="<em>Core folder Image</em>" class="border-0" >}}
{{< img src="iosmodulesfolder.png" alt="Modules folder Image" caption="<em>Modules folder Image</em>" class="border-0" >}}

```Stucture
App 
│─── Core
│	│─── Controllers
│	│	│ 	...
│	│─── Extensions
│	│	│ 	...
│	│─── Models
│	│	│ 	...
│	│─── Resources
│	│	│ 	...
│	│─── Services
│	│	│ 	...
│	│─── Static Data
│	│	│─── Enum
│	│	│	│ 	...
│	│	│ 	...
│	│─── Subviews
│	│	│ 	...
│	│─── Utils
│	│	│ 	...
│	│─── ViewModels
│	│	│ 	...
│─── Modules
│	│─── Login (example module name)
│	│	│─── Models
│	│	│	│ 	...
│	│	│─── Subviews
│	│	│	│ 	...
│	│	│ 	 LoginViewController
│	│	│	 LoginViewController.xib
│	│	│	 LoginnViewModel
```

| Folder | Description |
|-----|-----|
| **Core** | Is a subpackage for core and common class |
| **Core/Controllers** | Is a subpackage for base controllers class |
| **Core/Extensions** | Is a subpackage for extension class |
| **Core/Models** | Is a subpackage for class model |
| **Core/Resources** | Is a subpackage for external files |
| **Core/Services** | Is a subpackage for all background related service packages/classes |
| **Core/Static Data** | Is a subpackage for static data class/function |
| **Core/Static Data/Enums** | Is a subpackage for static data enum type |
| **Core/Subviews** | Is a subpackage for ui subclass of UIView |
| **Core/Utils** | Is a subpackage for used global helper functions in module |
| **Core/ViewModels** | Is a subpackage for base class of view |
| **Modules** | Is a subpackage for class modules |


## Security

1. Keychain
2. Jailbreak Detection

## Documentation

- General function and method
- Flow method

## Best Practice

- Environment: Scheme
- Style Guide: [Airbnb](https://github.com/airbnb/swift)  
- [Swiftlint (Install to Mac/Use brew)](https://github.com/realm/SwiftLint)

## Best Practice

- Memory management using Instrument

## Must Have Features

- Deeplink
- Crashlytics
- Analytics
- Firebase Performance
- Versioning and Force update mechanism -> store update (optional) (There is an option for tolerance updates)

## Third Party

- [Alamofire](https://github.com/Alamofire/Alamofire)
- [RX](https://github.com/ReactiveX/RxSwift)
- [Snapkit](https://github.com/SnapKit/SnapKit)
- [Kingfisher](https://github.com/onevcat/Kingfisher)
- Dependency Injection
- Firebase crashlytics
- Firebase analytics
- Firebase performance
- [Version](https://github.com/mxcl/Version)

## Optional Third Party

- [Realm](https://docs.mongodb.com/realm-sdks/swift/latest/)
- [Eureka](https://github.com/xmartlabs/Eureka)
- [Floating Panel](https://github.com/scenee/FloatingPanel)
- [SkeletonView](https://github.com/Juanpe/SkeletonView)