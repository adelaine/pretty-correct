---
name: apply-code-formatting
description: Apply and verify existing ESLint and Prettier settings without changing user preferences. Analyze code and select maintained language/framework presets only when settings are missing, empty, or the user explicitly requests a settings review. Use for linting and formatting setup, configuration changes, and repository-wide formatting.
---

# Apply Code Formatting

Produce a reproducible linting and formatting setup appropriate to the repository. Be strict about correctness, coverage, and verification, not about choosing the preset with the most rules. Do not treat `recommended`, `strict`, or `all` as universally best.

## Choose the permitted workflow first

Locate the effective ESLint and Prettier settings, including package-level configuration, inherited or shared configurations, workspace settings, and EditorConfig. Inspect repository instructions and working-tree changes before running tools. Evaluate each tool separately; a missing Prettier configuration does not authorize redesigning an existing ESLint setup.

**Default: run existing settings.** Use the repository's existing lint/fix and format/check commands within the requested scope, then follow the verification section. Do not analyze the code to select replacement rules, refresh presets, or change dependencies merely because a newer setup is available. If execution fails, report or address the execution problem within scope; failure alone does not authorize a settings review or weakening rules.

**Analyze code and select settings only if** the relevant settings are absent, empty, or the user explicitly asks to check the settings. A configuration that delegates to a shared preset is not empty. Configuration length does not justify reviewing or replacing existing settings.

**Preserve user preferences and overrides in every workflow.** Never change or remove them unless instructed, including when they repeat defaults or appear redundant. New imported presets must not silently supersede existing overrides. A general settings review permits evaluating and reporting on preferences, not changing them. A specific preference edit authorizes only that edit, not an unsolicited configuration review.

Read language and framework references only when needed for permitted configuration work or a concrete execution/verification issue. Otherwise, proceed directly to applying and verifying the existing setup. Read-only requests still authorize no mutation.

## Analyze before deciding (only when permitted above)

1. Confirm the target repository and requested scope. Read its instructions and inspect working-tree changes. Do not configure an adjacent repository by inference or overwrite unrelated work.
2. Inspect manifests, lockfiles, runtime requirements, existing configurations, scripts, CI, generated files, and representative source. Identify languages, frameworks, browser/server boundaries, embedded scripts, templates, and tests. Do not infer the stack from the repository name alone.
3. Read only the applicable references below. Verify compatible package versions, preset exports, parser requirements, and formatter support against the installed packages and current maintainer documentation before changing configuration.
4. Choose maintained presets based on the code and explain the choice briefly. Prefer useful correctness checks and framework coverage; add opinionated restrictions only when supported by the task or established conventions. Record existing check failures before applying changes where practical.
5. For template or content-heavy applications, capture a baseline build or representative rendered output before broad formatting. Keep comparison artifacts outside authored source and separate existing build warnings from regressions.

## Select references

Language guides:

- [JavaScript](references/languages/javascript.md): JavaScript modules and runtime environments.
- [TypeScript](references/languages/typescript.md): typed presets, project boundaries, and type checking.
- [Markup and content](references/languages/markup-and-content.md): HTML, CSS, JSON, YAML, Markdown, and MDX.

Framework and integration guides:

- [React](references/frameworks/react.md): JSX/TSX, Hooks, accessibility, and framework presets.
- [Astro](references/frameworks/astro.md): components, extracted scripts, and content builds.
- [Vue](references/frameworks/vue.md): single-file components and nested parsers.
- [Svelte](references/frameworks/svelte.md): component-aware linting and formatting.
- [Tailwind CSS](references/frameworks/tailwindcss.md): stylesheet-aware class sorting.

For an unlisted language or framework, discover its maintained integration through official documentation. Do not force ESLint onto unsupported languages or claim Prettier covers formats without a compatible parser. State coverage limits and use existing native tooling where appropriate; do not introduce a different toolchain without task justification.

## Recheck references, not remembered locations

Resolve local links relative to the actual loaded `SKILL.md`, never a remembered absolute installation path. On a missing reference, inspect this skill's current file tree and search by topic or filename. Read the discovered replacement and verify its scope; do not silently skip guidance or substitute a similarly named file from another skill. If no replacement exists, consult authoritative upstream documentation and disclose the missing local guide.

Upstream URLs are discovery starting points, not permanent contracts. When rechecking, follow redirects and confirm the owner, project, topic, and applicable version. If a page moved or disappeared, navigate the maintainer's current documentation or repository metadata and search that authoritative site. Verify exports in the installed package rather than copying examples for a different release. If verification is unavailable, state the uncertainty and avoid a speculative migration. Repair local reference links when updating this skill itself, not an unrelated installed copy during project work.

## Compose configuration

- Import or extend the language's maintained shared configuration and the applicable framework presets. Do not copy their full rule lists into project files or these references. Preserve established shared configurations unless the task warrants replacing them.
- Scope each preset, parser, processor, and runtime global set to the files it actually supports. Preserve framework parsers when layering TypeScript support. Do not accidentally apply project-based checks to virtual files outside the project.
- Layer configuration in this order: language presets, framework integrations, narrowly scoped project adaptations, then user preferences. Put lint preferences after the presets they override. Keep formatting preferences in Prettier, and finish ESLint composition with the compatible `eslint-config-prettier` configuration so conflicting formatting rules stay disabled.
- Label project adaptations and user overrides separately. Explain non-obvious overrides with a concise comment describing the reason. Use neutral labels such as `User preferences`; do not insert personal names unless explicitly requested.
- For new settings, inherit defaults when they already match the request and add only needed preference overrides. Preserve existing preferences and overrides, even redundant ones, unless their change or removal is instructed. Do not infer personal settings from another project. Distinguish indentation width from tabs versus spaces. Check existing EditorConfig and editor settings for conflicts before claiming effective behavior.
- Preserve the package manager and lockfile. Verify peer dependencies and runtime compatibility; do not bypass conflicts with forced installs or silently upgrade unrelated application dependencies. Pin Prettier and its formatting plugins to avoid unexpected output changes. Explain any required runtime-support change.
- Define ignores from actual generated, vendored, cache, and external-resource paths. Do not exclude authored source to make checks pass. Ensure new configuration and ignore files are trackable despite broad repository ignore patterns.
- Keep formatting and linting as separate commands. Provide check and fix/write commands, and integrate them with existing validation or CI when setup is requested. An analysis-only or links-only request authorizes no edits, installs, or fixes.

## Apply and verify

1. Run scoped, locally installed tools using the repository's package manager and existing commands when available. Use existing settings unchanged unless configuration work is permitted by the workflow gate. Review lint fixes before retaining them; never disable correctness rules merely to obtain a passing run. Keep behavior changes necessary to resolve findings explicit and narrowly scoped.
2. Apply formatting to the authorized files. Inspect the diff for unrelated edits, damaged content, changed markup, and unintended dependency changes. A formatter is not proof of semantic equivalence.
3. Run formatting checks, linting, and relevant type or framework checks. For template or content transformations that could change rendering, compile/build and compare affected output against the baseline. Check structure and text, not merely build success; normalize only known non-semantic differences such as generated asset identifiers. Fix formatting-induced changes, then repeat the affected checks until output is stable. Separate pre-existing failures from introduced failures.
4. Verify that each intended file type is actually processed, including embedded scripts where applicable. Use effective-configuration inspection or a small non-persistent lint probe when coverage is uncertain; a successful command that ignored the source is not sufficient.
5. Report the selected setup, applied preferences, validation results, and material limits. Do not claim success for checks that were skipped or failed. Leave changes uncommitted unless commit or push is explicitly requested.
