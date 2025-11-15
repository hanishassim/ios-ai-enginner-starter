
You're analyzing an **iOS (Swift) codebase** with the goal of understanding its structure and major concerns. The tech stack is summarized in `./{results_folder}/1-techstack.md`. Categorized files are listed in `./{results_folder}/2-file-categorization.json`.

> This task may take some time — that is expected and acceptable.
> Do **not** skip files or produce partial results due to time or complexity. Accuracy and completeness are **mission-critical**.
> You are permitted to take as long as necessary to:
>
>   * Review every relevant file
>   * Extract actual patterns and conventions
>   * Produce complete, high-fidelity output
>
> If a file is listed in `./{results_folder}/2-file-categorization.json` or is part of a relevant domain, it **must** be included in your analysis.
> Do not optimize for speed or brevity. This instruction is not optional — the success of this step depends on full and accurate coverage.


### Your Task

Determine which architectural domains are present in the project. Consider:

* **File structure and naming patterns:** (e.g., feature-first `Features/FeatureName/` vs. layer-first `Screens/`, `Views/`, `ViewModels/`, `Services/`)
* **Framework conventions:** (e.g., use of SwiftUI Views, UIKit ViewControllers, ObservableObject, Combine)
* **Imports and usage patterns:** (e.g., consistent imports from `Combine`, `SwiftUI`, `Foundation`, third-party libraries)
* **Configuration files:** (e.g., `Info.plist`, `Package.swift`, `Podfile`)
* **Common architectural markers:** (e.g., `Screens/`, `Views/`, `ViewModels/`, `Models/`, `Services/`, `Repositories/`, `Routing/`, `Themes/`, etc.)


### Critical Analysis - Mandatory vs Optional Patterns

For each domain you identify, determine:

* **REQUIRED**: Which services, view models, classes, or patterns are consistently used across the codebase and appear to be architectural requirements?
* **CONSTRAINTS**: What types of implementations are clearly expected? (e.g., "all screens must use a ViewModel for state management", "all data fetching must go through a Service or Repository", "all data models must be immutable structs")


### Example Domains to Detect

You do not need to detect all of these — only include what's truly present.
There may also be domains that aren't listed here but are relevant to this specific project. Include any meaningful domains you identify.

* **ui:** Screens, SwiftUI Views, UIKit ViewControllers, or rendering logic.
* **routing:** App navigation (e.g., NavigationView, UINavigationController, custom routers).
* **theme:** Shared visual styling, custom themes, design tokens.
* **state_management:** Centralized or local state (e.g., ObservableObject, Combine, ViewModels).
* **data_layer:** Persistence and data-fetching (e.g., Repositories, Services, URLSession, Alamofire).
* **local_storage:** Database or local persistence (e.g., Core Data, Realm, UserDefaults).
* **domain:** Core business logic and data models (structs/classes).
* **di:** Dependency Injection setup (e.g., Swinject, Resolver, manual DI).
* **auth:** Authentication / access control logic.
* **error_handling:** Standardized error classes or handling mechanisms.


### Output

Write a JSON object to `./{results_folder}/3-architectural-domains.json` like so:

```json
{
  "state_management": {
    "required_patterns": {
      "screen_state": "Screens and views use a ViewModel conforming to ObservableObject for state",
      "form_state": "Forms use local @State or ViewModel properties"
    },
    "architectural_constraints": {
      "ui_dependency": "Views must not directly instantiate services; must use dependency injection or environment objects",
      "immutability": "State models (e.g., 'LoginState') should be immutable structs or classes"
    }
  },
  "data_layer": {
    "required_patterns": {
      "data_fetching": "Must use a Service or Repository pattern (e.g., 'ProductRepository')",
      "api_calls": "Must use a centralized networking service (e.g., URLSession, Alamofire)"
    },
    "architectural_constraints": {
      "error_handling": "Repositories/Services are responsible for catching exceptions and returning a Result type or error object"
    }
  }
}
```


Only include domains you find concrete evidence for based on the actual codebase.

This analysis will help ensure future additions follow the established architectural patterns (MVVM for iOS) rather than introducing inconsistent approaches.
After writing ./{results_folder}/3-architectural-domains.json, read the contents of [./4-domain-deep-dive.md](4-domain-deep-dive.md) and proceed accordingly with {results_folder} as the `results_folder`.