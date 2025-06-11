# Integration Guide

## For Package Users

When you install this package via npm, follow these steps:

### 1. Install the package
```bash
npm install @your-org/base-scss
```

### 2. Create your theme structure
```
your-project/
├── scss/
│   ├── theme/
│   │   ├── _index.scss
│   │   └── _overrides.scss
│   └── style.scss
```

### 3. Set up your theme/_index.scss
```scss
@forward "@your-org/base-scss/variables";
@forward "@your-org/base-scss/mixins";
@forward "@your-org/base-scss/functions";
@import './overrides';
```

### 4. Create your theme/_overrides.scss
Copy the template from the package and customize as needed:
```scss
// Your custom variable overrides
$secondary-l: 0.41;
$font-family-base: 'Your Font';
$font-size-base-px: 18;
$max-wrapper-width: 1200px;
// Add more overrides as needed
```

### 5. Import in your main SCSS file
```scss
@import "./base/base";  // This will use your theme via relative import

// Your site-specific styles below
@layer site {
  // Your styles here
}
```

## For Package Development

The current structure during development uses relative imports. Before publishing:

1. Update theme/_index.scss to remove relative imports
2. Document the expected user structure
3. Test with actual npm link/publish workflow

## Build Pipeline Integration

Make sure your build process includes:
```json
{
  "scripts": {
    "build:sass": "npx sass --watch src/scss/style.scss:src/css/style.css --style=expanded --source-map"
  }
}
```
