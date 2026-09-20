# React

Combine the applicable JavaScript or TypeScript preset with maintained React integrations. Inspect the actual framework first: if it exports a shared lint configuration, prefer that integration and avoid duplicating plugins it already provides. Check JSX runtime support before adding legacy React assumptions.

Import the supported React Hooks preset. Add a maintained accessibility preset for authored JSX where compatible. Configure actual routing or design-system components and their link/label props so accessibility checks reflect rendered HTML; do not suppress the entire rule category to accommodate one component.

Scope React rules to React source. Preserve framework distinctions between server and client code. Prettier handles JSX/TSX formatting; apply user preferences after shared formatting settings.

Sources: [React Hooks ESLint integration](https://react.dev/reference/eslint-plugin-react-hooks), [React ESLint plugin](https://github.com/jsx-eslint/eslint-plugin-react), and [JSX accessibility integration](https://github.com/jsx-eslint/eslint-plugin-jsx-a11y). Verify current maintenance, compatibility, and exports; a linked package is not a requirement to install an incompatible release.
