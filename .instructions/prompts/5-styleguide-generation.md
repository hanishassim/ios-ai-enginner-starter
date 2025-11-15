> This task may take time — that is expected and required.


You are a senior **iOS engineer** responsible for generating style guides that explain what makes this codebase unique for each category listed in `./{results_folder}/2-file-categorization.json`. Given the best practices and guidelines you create, anyone should be able to create a file of that category that matches the existing conventions.

All style guides must follow the [Google Swift Style Guide for iOS](https://google.github.io/swift/) as the baseline. Highlight any unique conventions or deviations from this guide that are present in the codebase.

## Requirements

You must:

* Review **every individual Swift file** listed under each category.
* Identify only the **unique and distinctive patterns** that make this project stand out from standard iOS/Swift conventions and the Google Swift Style Guide.
* Focus on project-specific approaches, custom patterns, and non-standard implementations (e.g., custom base classes, specific ViewModel naming, unique dependency injection, custom error handling).
* Create **one markdown file per category** highlighting only these unique conventions.

⚠️ You must create a separate file for **each category**, with no omissions.

## Required Output Files


For example, if the categories are:

* `screens`
* `views`
* `services`
* `state_management`

Then you must create:

* `./{results_folder}/5-style-guides/screens.md`
* `./{results_folder}/5-style-guides/views.md`
* `./{results_folder}/5-style-guides/services.md`
* `./{results_folder}/5-style-guides/state_management.md`

## Important Guidelines

* Do **not** skip a single category. Partial output is unacceptable.
* Do **not** include common industry patterns (like standard SwiftUI View usage or Google Swift Style Guide defaults) — only extract the conventions that are **unique to this specific codebase**.
* Do **not** invent patterns — only use what is observed in the codebase.

After writing each of the domain files, read the contents of [./6-build-instructions.md](6-build-instructions.md) and proceed accordingly with {results_folder} as the `results_folder`.
