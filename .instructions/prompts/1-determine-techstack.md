
Determine the type of iOS project and summarize the tech stack. Your summary should include:

### 🚀 iOS Tech Stack Analysis

* **Programming Language:** (e.g., Swift)
* **Primary Framework:** (e.g., UIKit, SwiftUI)
* **State Management:** (e.g., ObservableObject, Combine, Delegation)
* **Architecture Pattern:** (e.g., MVVM, MVC, VIPER)
* **Navigation:** (e.g., NavigationView, UINavigationController)
* **Dependency Injection:** (e.g., Resolver, Swinject)
* **Backend / Database:** (e.g., Firebase, Core Data, Realm, CloudKit)
* **Key Packages:** (e.g., Alamofire for networking, Codable for models, FirebaseAuth for auth)

### 🎯 Domain Specificity Analysis

* **What specific problem domain does this application target?** (e.g., "fintech app", "e-commerce storefront", "productivity tool", "social media client")
* **What are the core business/app concepts?** (e.g., "interest calculation", "product catalog management", "task scheduling", "user content feeds")
* **What type of user interactions does it support?** (e.g., "data entry forms", "shopping cart workflows", "list scrolling and filtering", "real-time chat")
* **What are the primary data models (Swift classes/structs)?** (e.g., `AuthEntity`, `AuditDeviceEntity`, `UnlockDataEntity`, `FirmwareEntity`)

###  boundaries Application Boundaries

* **What features/functionality are clearly within scope based on existing code?** (e.g., "offline-first data entry", "user authentication", "displaying lists of data")
* **What types of features would be architecturally inconsistent with the current design?** (e.g., "adding real-time multiplayer features to a single-user, offline-first app", "adding complex payment processing to a simple content-viewing app")
* **Are there any specialized libraries that suggest domain constraints?** (e.g., `flutter_map` suggests GIS/location focus, `in_app_purchase` suggests monetization, `flame` suggests a game, `tflite_flutter` suggests on-device ML).

Add all your findings to `./{results_folder}/1-techstack.md`

The domain analysis should help future prompts understand what types of new features would fit vs. conflict with the existing application architecture.

Once completed read [./2-categorize-files.md](2-categorize-files.md) and continue on accordingly with {results_folder} as the `results_folder`