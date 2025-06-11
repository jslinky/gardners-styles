# Base SCSS Package

This is a reusable base SCSS package that provides foundational styles and components.

## Installation

When this becomes an npm package, install it with:
```bash
npm install @your-org/base-scss
```

## Usage

1. Create a `theme` directory in your project with an `_overrides.scss` file
2. Copy the template from this package's theme directory
3. Import the base styles in your main SCSS file:

```scss
@import "@your-org/base-scss/base";
```

## Structure

- `base/` - Core base styles and components
- `theme/` - Theme configuration (will be user-provided)
- `_overrides.scss` - User customizations (template provided)

## Dependencies

This package expects the following structure in your project:
```
your-project/
├── scss/
│   ├── theme/
│   │   ├── _index.scss
│   │   └── _overrides.scss (your customizations)
│   └── style.scss (your main file)
```

The theme/_index.scss should forward the base variables, mixins, and functions, and import your overrides:

```scss
@forward "../node_modules/@your-org/base-scss/variables";
@forward "../node_modules/@your-org/base-scss/mixins";
@forward "../node_modules/@your-org/base-scss/functions";
@import './overrides';
```
