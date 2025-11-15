
You are a senior iOS developer responsible for categorizing every file in the codebase. You’ve been informed that the project is defined as: `./{results_folder}/1-techstack.md` (read this file first).

Your task:


* Visit every Swift file in the main source directory (typically `Sources/` or `App/`) and any other relevant project files (like `Info.plist`, `Package.swift`, or `Podfile`).
* You **must** ignore auto-generated files from the build process (like `DerivedData/`, `build/`) and dependency files (`Pods/`, `Package.resolved`).
* Categorize each file based on its role, such as: `screens`, `views`, `viewModels`, `models`, `services`, `repositories`, `state_management`, `utils`, `constants`, `routing`, `themes`, `main`, etc.


Output the file categorization as a JSON file at:
`./{results_folder}/2-file-categorization.json`

```json
{
  "main": ["./App/AppDelegate.swift"],
  "screens": ["./App/Features/Auth/LoginView.swift"],
  "views": ["./App/Views/AppVersionView.swift"],
  "models": ["./App/Models/Firmware.swift"],
  "state_management": ["./App/ViewModels/ActivityViewModel.swift"],
  "services": ["./App/Services/APIService.swift"],
  "routing": ["./App/Routing/AppRouter.swift"]
}
```


A single file can appear in multiple categories if appropriate (e.g., a file might define both a `view` and its `state_management` ViewModel).


> This task may take some time — that is expected and acceptable.
> Do **not** skip files or produce partial results due to time or complexity. Accuracy and completeness are **mission-critical**.
> If a file is listed in `./{results_folder}/2-file-categorization.json` or is part of a relevant domain, it **must** be included in your analysis.
> Do not optimize for speed or brevity. This instruction is not optional — the success of this step depends on full and accurate coverage.

You are permitted to take as long as necessary to:

* Review every relevant file.
* Extract actual patterns and conventions.
* Produce complete, high-fidelity output.


After writing ./{results_folder}/2-file-categorization.json, read the contents of [./3-identify-architecture.md](3-identify-architecture.md) and proceed accordingly with {results_folder} as the `results_folder`.