# Vue

Import the maintained Vue preset appropriate to the project's Vue version and linting goals. Combine it with the language baseline without replacing the Vue single-file-component parser. Delegate script parsing to the supported TypeScript parser when needed, following the installed plugin's documentation.

Check template and script coverage independently. Respect framework-provided shared configuration and compiler macros. Keep formatting in Prettier, with user preferences after any shared formatter settings and ESLint formatting conflicts disabled. Run the project's Vue-aware type checker and relevant build after applying changes.

Sources: [Vue ESLint user guide](https://eslint.vuejs.org/user-guide/) and [Vue tooling guidance](https://vuejs.org/guide/scaling-up/tooling.html). Follow current maintainer links if locations or exported presets change.
