# Astro

Import the maintained Astro ESLint preset in addition to the applicable language configuration. Preserve the Astro parser and script processor. Verify coverage of both component frontmatter and extracted browser scripts; virtual script paths may not belong to the TypeScript project. Use scoped syntax-only linting there when required and retain the framework type checker.

Add the maintained Astro Prettier plugin and its documented parser selection. Compose accessibility and client-framework presets only for applicable markup and islands. Do not apply React assumptions to Astro templates.

Use the framework's synchronization and checking commands as appropriate for a clean checkout. When formatting Astro or MDX changes whitespace or element layout, build and inspect affected rendered markup. Read the content guide for MDX-specific behavior.

Sources: [Astro editor setup](https://docs.astro.build/en/editor-setup/), [Astro ESLint integration](https://ota-meshi.github.io/eslint-plugin-astro/user-guide/), and [Astro Prettier plugin](https://github.com/withastro/prettier-plugin-astro). Recheck current documentation and package compatibility rather than preserving a hard-coded version matrix.
