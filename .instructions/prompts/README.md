# Instruction Generation Prompt Chain

This project includes an AI-driven prompt workflow that examines a codebase’s architecture, recurring patterns, and overall purpose to automatically create a detailed instructions document named `{final_output_file}.md` (e.g., `copilot-instruction.md`).


## Overview

This prompt sequence walks an AI system through a set of organized stages to pull out valuable information from a codebase. It can:

* Detect the core technologies and primary frameworks in use
* Analyze file roles and outline the overall project layout
* Derive architectural choices and common design approaches
* Grasp domain-specific ideas and essential functionalities
* Produce recommendations on coding style and project structure for upcoming contributions


The generated `{final_output_file}.md` file (its name is provided as an input parameter to the AI Agent) acts as a top-level reference and onboarding guide, ensuring that any AI-produced code follows the project’s established patterns, conventions, and overall design direction.


## Prerequisites

This prompt chain is expected to be provided the following:

- {output_folder} - A path to the folder where generated instruction files will be saved (e.g., `.results/`)
- {final_output_file} - A file which combines all the work that's been done into a single place eg., `/.github/copilot-instructions.md`)

### Folders and setup
- {output_folder} - `.instructions/results`
- {final_output_file} - `/.github/copilot-instructions.md`


## Agent Mode Capabilities

The AI agent executing this prompt chain is expected to support the following capabilities:

- Reading and writing individual files
- Reading and writing entire folders
- Analyzing code structure, file organization, and implementation patterns
- Identifying and understanding technology stacks, frameworks, and libraries
- Generating structured instruction files based on project analysis



## Prompt

```
{output_folder} = .instructions/results
{final_output_file} = /.github/copilot-instructions.md

You are assisting with generating a {final_output_file} file using a multi-step prompt chain.

1. Navigate to the `.instructions/prompts` folder
2. Review all the prompt files in this folder WITHOUT executing them. 
    - This will help you understand the full scope of the prompt chain.
3. Confirm you have a full understanding of the prompt chain sequence.
4. Once you're familiar with the flow, begin executing the prompts in numerical order:
    - 1-determine-techstack.md
    - 2-categorize-files.md
    - 3-identify-architecture.md
    - 4-domain-deep-dive.md
    - 5-styleguide-generation.md
    - 6-build-instructions.md
5. For each step, output results into a corresponding `{output_folder}/` folder.
    - Mirror the step’s filename e.g., `1-determine-techstack.md` > `{output_folder}/1-determine-techstack.md`.

Stop ONLY when:
    - All `instruction-generation` steps are complete
    - A full `{final_output_file}` can be generated.
```


## Execution

When given an {output_folder}, the AI agent will perform the following steps, reading each file and following it's instructions in order:

- [./1-determine-techstack.md](./1-determine-techstack.md)
  - Analyzes the codebase to identify the technology stack, frameworks, and libraries being used
- [./2-categorize-files.md](./2-categorize-files.md)
  - Categorizes and organizes files by their purpose and functionality
- [./3-identify-architecture.md](./3-identify-architecture.md)
  - Examines the project structure and identifies architectural patterns and design decisions
- [./4-domain-deep-dive.md](./4-domain-deep-dive.md)
  - Analyzes the business domain and understands the application's core functionality
- [./5-styleguide-generation.md](./5-styleguide-generation.md)
  - Generates style guidelines and coding standards based on existing code patterns
- [./6-build-instructions.md](./6-build-instructions.md)
  - Identifies key features and capabilities of the application and creates the application's instruction file

Each prompt should be provided with the {output_folder} parameter to ensure consistent output location.