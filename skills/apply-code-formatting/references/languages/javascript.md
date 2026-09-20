# JavaScript

Inspect module formats and browser, server, worker, and test environments before assigning globals. Import the maintained core preset from `@eslint/js`, then compose project/framework presets; do not enumerate its rules. Scope globals to their actual runtime so browser code does not accidentally accept server-only identifiers.

Use the configuration format supported by the installed ESLint and module system. Prefer flat configuration for new supported setups; assess an existing legacy setup before migrating it. Keep Prettier responsible for layout and quotes, with user preferences following any shared formatter configuration.

Recheck configuration exports and runtime requirements using [ESLint configuration documentation](https://eslint.org/docs/latest/use/configure/configuration-files). Verify formatting compatibility with [Prettier's linter integration guide](https://prettier.io/docs/integrating-with-linters). Follow the relocation procedure in `SKILL.md` if these sources move.
