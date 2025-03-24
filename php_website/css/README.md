# CSS Structure Documentation

This directory contains the CSS files for the UNM Prep website. The CSS is organized into a modular structure for better maintainability and scalability.

## Directory Structure

```
css/
├── components/           # Component-specific styles
│   ├── buttons.css      # Button styles
│   ├── forms.css        # Form styles
│   ├── navigation.css   # Navigation and header styles
│   └── cards.css        # Card and grid layout styles
├── layouts/             # Layout-specific styles
│   └── responsive.css   # Responsive design and media queries
├── utilities/           # Utility styles and variables
│   ├── variables.css    # CSS variables and custom properties
│   ├── reset.css        # CSS reset styles
│   └── animations.css   # Animation and utility classes
└── main.css            # Main CSS file that imports all components
```

## Usage

### Including CSS in HTML

Add the following line to your HTML files to include the CSS:

```html
<link rel="stylesheet" href="css/main.css">
```

### CSS Variables

The website uses CSS variables for consistent styling. These are defined in `utilities/variables.css`:

```css
:root {
    /* Colors */
    --primary-color: #4a90e2;
    --secondary-color: #2c3e50;
    --accent-color: #e74c3c;
    
    /* Backgrounds */
    --background-light: #ffffff;
    --background-dark: #f8f9fa;
    
    /* Text Colors */
    --text-primary: #333333;
    --text-secondary: #666666;
    
    /* Spacing */
    --spacing-xs: 0.25rem;
    --spacing-sm: 0.5rem;
    --spacing-md: 1rem;
    --spacing-lg: 1.5rem;
    --spacing-xl: 2rem;
    
    /* Border Radius */
    --radius-sm: 4px;
    --radius-md: 8px;
    --radius-lg: 16px;
    --radius-full: 9999px;
    
    /* Shadows */
    --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
    --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.1);
    --shadow-lg: 0 10px 15px rgba(0, 0, 0, 0.1);
}
```

### Component Classes

#### Buttons
```html
<button class="btn btn-primary">Primary Button</button>
<button class="btn btn-secondary">Secondary Button</button>
```

#### Forms
```html
<div class="form-group">
    <label for="name">Name</label>
    <input type="text" class="form-control" id="name">
</div>
```

#### Cards
```html
<div class="card">
    <div class="card-header">Card Title</div>
    <div class="card-body">Card Content</div>
    <div class="card-footer">Card Footer</div>
</div>
```

#### Navigation
```html
<nav class="main-nav">
    <a href="#" class="nav-link">Home</a>
    <a href="#" class="nav-link">About</a>
    <a href="#" class="nav-link">Contact</a>
</nav>
```

### Utility Classes

The website includes various utility classes for common styling needs:

#### Spacing
```html
<div class="m-3">Margin 3</div>
<div class="p-2">Padding 2</div>
```

#### Flexbox
```html
<div class="d-flex justify-content-center align-items-center">
    Centered Content
</div>
```

#### Text
```html
<div class="text-center text-primary">Centered Primary Text</div>
```

#### Background
```html
<div class="bg-primary">Primary Background</div>
```

### Responsive Design

The website is fully responsive with breakpoints at:
- Extra small: < 576px
- Small: ≥ 576px
- Medium: ≥ 768px
- Large: ≥ 992px
- Extra large: ≥ 1200px

### Accessibility

The CSS includes several accessibility features:
- High contrast color combinations
- Focus styles for keyboard navigation
- Reduced motion support
- Print styles
- Dark mode support

### Browser Support

The CSS is compatible with:
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Opera (latest)

### Contributing

When adding new styles:
1. Use CSS variables for colors, spacing, and other common values
2. Follow the existing naming conventions
3. Add appropriate comments
4. Include responsive styles
5. Test across different browsers and devices

### Best Practices

1. Use semantic class names
2. Keep specificity low
3. Use CSS variables for consistent values
4. Include responsive styles
5. Test accessibility
6. Document new components
7. Follow the existing structure 