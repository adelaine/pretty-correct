# Markup and Content

Inventory HTML, stylesheets, structured data, Markdown, and MDX separately. Prettier formatting support does not imply ESLint coverage. Use existing native linting or a maintained language plugin only when the task calls for it; import its supported preset instead of copying rule definitions.

Select parsers from actual file formats. Do not treat MDX as plain JSX, JSON with comments as strict JSON, or framework templates as generic HTML. Preserve meaningful whitespace, frontmatter, code fences, directives, and embedded language boundaries.

For MDX, inspect rendered output when wrapping JSX text: moving text onto separate lines can introduce Markdown paragraph nodes. Preserve the intended structure with the smallest supported change, such as an explicit JSX text expression or targeted formatting exclusion with a reason. Do not mass-rewrite content or exclude all MDX solely to avoid investigating a rendering change.

Check JSON/YAML and workflow validity after formatting. Leave generated files, vendored assets, and lockfiles to their owners unless explicitly in scope.

Sources: [Prettier configuration](https://prettier.io/docs/configuration), [supported languages](https://prettier.io/docs/), and [MDX syntax](https://mdxjs.com/docs/what-is-mdx/). Recheck current source locations through the owning project when links move.
