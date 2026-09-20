# TypeScript

Read the JavaScript guide as the base. Inspect `tsconfig` inheritance, project references, strictness, included files, and framework-generated types.

Import a `typescript-eslint` shared preset rather than reproducing its rules. Compare the supported syntax-only and type-aware presets against the code. Prefer type-aware correctness checks when project information can be resolved reliably; evaluate stricter presets for useful additional coverage rather than choosing them by name. Explain any deliberate syntax-only boundary.

Use the installed version's supported project-service or project configuration. Keep JavaScript tooling files and framework virtual scripts outside typed checks unless correctly included. Do not expand a default project over the whole repository to hide project-resolution errors. Generate required framework types before linting on a clean checkout.

Preserve framework parsers and configure their TypeScript delegation as documented. Run the compiler or framework checker separately; ESLint is not a replacement for type checking. Apply user lint overrides after the selected presets and formatting preferences in Prettier.

Sources: [shared presets](https://typescript-eslint.io/users/configs/), [typed linting](https://typescript-eslint.io/getting-started/typed-linting/), and [typed-linting troubleshooting](https://typescript-eslint.io/troubleshooting/typed-linting/). Reverify current locations and version applicability as directed by `SKILL.md`.
