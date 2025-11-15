
You are a senior AI engineer responsible for bootstrapping a project-specific AI agent experience for an **iOS (Swift) project**. The goal is to generate a markdown instruction file at:

`{final_output_file}`

This file will serve as a reusable meta-instruction for any AI assistant to generate **consistent, convention-following features** in this Flutter codebase.

You must synthesize the following source materials:

* `./{results_folder}/1-techstack.md`: Provides tech choices (Dart, Flutter, state management) and domain boundaries.
* `./{results_folder}/2-file-categorization.json`: Lists the file categories (e.g., `screens`, `widgets`, `services`, `state_management`) and their canonical examples.
* `./{results_folder}/5-style-guides/{category}.md`: Describes unique conventions for each file category.
* `./{results_folder}/3-architectural-domains.json`: Defines how domains like `ui`, `routing`, `data_layer`, `state_management`, etc., are implemented, along with constraints and required patterns.

---

## Your Output: `{final_output_file}`

This file must include:

---

### 1. **Overview Section**

Explain the purpose of this file:

* It enables AI coding assistants to generate new **Swift/iOS** features aligned with the project’s architecture and style.
* It is based only on actual, observed patterns from the codebase — not invented practices.

---

### 2. **File Category Reference**


For each category in `2-file-categorization.json`:

* Explain what it is (e.g., "Screens/Views," "Data models," "ViewModels," "Services").
* List 1–2 representative file examples (e.g., `App/Features/Auth/LoginView.swift`).
* Summarize key conventions based on its corresponding `5-style-guides/{category}.md`.

---

### 3. **Feature Scaffold Guide**

Define how to plan and implement a new feature. Include:


* How to determine which categories of files to create (e.g., a new feature needs a `View`, a `ViewModel`, and maybe a `Service`).
* Where to place those files (e.g., "All new features must be in `App/Features/<FeatureName>/...`").
* How to follow naming and structure conventions (e.g., `MyFeatureView.swift`, `MyFeatureViewModel.swift`).
* Example: what files to create for a new **screen/view**, its **state management (ViewModel)**, and any associated **unit/UI tests**.

This section should refer to actual conventions in the project (e.g., if a feature-first-layout is used, mention creating the `Features`, `Models`, `ViewModels`, and `Services` folders).

---

### 4. **Integration Rules**


From `3-architectural-domains.json`, summarize constraints like:

* "All stateful screens/views must use a ViewModel conforming to ObservableObject."
* "All business logic must be in a ViewModel or Service, not in the View file."
* "All API requests must go through a Service or Repository class."
* "All data models must be immutable (e.g., using Swift structs)."

This prevents LLMs from generating non-compliant or inconsistent files.

---

### 5. **Example Prompt Usage**


Show how a user could prompt an AI assistant with a request like:

> "Create a new view called 'UserSettings' that allows users to update their profile."

And have it respond with a plan to create:

* `App/Features/Settings/UserSettingsView.swift`
* `App/Features/Settings/UserSettingsViewModel.swift`
* `App/Models/UserProfile.swift` (if models are feature-specific)
* `App/Features/Settings/Tests/UserSettingsViewTests.swift`
* etc…

Only use categories and file types present in this project.

---

## ⚠️ Requirements

* **Do not** include invented best practices.
* **Do not** list categories or conventions that aren’t supported by the codebase.
* **Do not** omit any categories or domains defined in the analysis.

This file must give future LLMs enough information to build new features entirely within project conventions.

To clarify further, if `{final_output_file}` already exists, overwrite it.