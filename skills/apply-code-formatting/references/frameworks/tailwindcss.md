# Tailwind CSS

When Tailwind is present and class sorting is within scope, use its maintained Prettier plugin rather than manually sorting utilities or recreating its order in lint rules. Verify the plugin loading order required by the installed release and other framework plugins.

Resolve the actual Tailwind configuration or stylesheet entry point for the installed major version. Do not copy a path from another project. Configure custom class helpers or attributes only when present and supported; do not assume all string constants contain utility classes. Apply user formatting preferences without replacing the plugin's maintained ordering algorithm.

Source: [Tailwind Prettier plugin](https://github.com/tailwindlabs/prettier-plugin-tailwindcss). Recheck its current README, entry-point options, and compatibility list when applying or revisiting the setup.
