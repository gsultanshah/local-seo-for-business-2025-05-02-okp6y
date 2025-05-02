# Landing Page Maintenance Guide

This guide provides detailed instructions for maintaining and customizing the BestLocalSEO landing page. Follow these steps to make common updates while preserving the page's functionality and design.

## Table of Contents
- [Updating Text and Styles](#updating-text-and-styles)
- [Managing Links](#managing-links)
- [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
- [Troubleshooting](#troubleshooting)

## Updating Text and Styles

### Header Section
The header contains the main navigation and logo. To update:

1. **Logo Text:**
```html
<!-- Find this line in the header -->
<a href="/" class="text-2xl font-bold text-blue-600">BestLocalSEO</a>
```
- Replace "BestLocalSEO" with your brand name
- Maintain the existing classes for consistent styling

2. **Navigation Menu Items:**
```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Features</a>
    <!-- Additional menu items -->
</div>
```
- Update text between `>` and `</a>` tags
- Keep the `href` attributes matching your section IDs

### Hero Section
Located at the top of the page under the header:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-extrabold text-gray-900 mb-8 tracking-tight">
    Local SEO for Business
</h1>
<p class="text-xl md:text-2xl text-gray-600 mb-12 leading-relaxed">
    Master your local search presence with our comprehensive SEO checklist and tools
</p>
```
- Update heading and paragraph text as needed
- Maintain responsive text classes (`text-4xl md:text-5xl lg:text-6xl`)
- Keep spacing classes (`mb-8`, `mb-12`) for proper layout

### Tailwind CSS Class Guide
Common classes used throughout the page:

```css
/* Text sizes */
text-sm    /* Small text */
text-xl    /* Large text */
text-2xl   /* Larger text */

/* Colors */
text-gray-600    /* Gray text */
text-blue-600    /* Blue text */
bg-white         /* White background */

/* Spacing */
px-4    /* Horizontal padding */
py-4    /* Vertical padding */
mb-8    /* Bottom margin */
```

## Managing Links

### Navigation Links
Current navigation links are:

```html
<div class="hidden md:flex space-x-8">
    <a href="#features">Features</a>
    <a href="#guide">Guide</a>
    <a href="#software">Software</a>
    <a href="#faq">FAQ</a>
</div>
```

To update:
1. Locate the link you want to change
2. Modify the `href` attribute:
   - For same-page sections: Use `#section-id`
   - For other pages: Use relative paths (`/about.html`)
   - For external links: Use full URLs (`https://example.com`)

### Call-to-Action Links
Located in hero and CTA sections:

```html
<a href="https://bestlocalseo.org/download" class="inline-flex items-center px-8 py-4 text-lg font-semibold text-white bg-blue-600 rounded-full">
    Download Free Checklist
</a>
```
- Update `href` with your download or signup URL
- Maintain all classes for consistent button styling

## Adding Privacy and Terms Pages

### Footer Modification
Add privacy and terms links to the footer:

1. Locate the footer links section:
```html
<div>
    <h4 class="text-lg font-semibold text-white mb-4">Quick Links</h4>
    <ul class="space-y-2">
        <!-- Add new links here -->
        <li><a href="/privacy.html" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="/terms.html" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

2. Create matching privacy.html and terms.html files in your root directory
3. Ensure consistent styling by copying the header and footer from index.html

## Troubleshooting

Common issues and solutions:

### Broken Links
- Check for typos in `href` attributes
- Verify file paths are correct
- Test all links after updating

### Styling Issues
- Make sure all Tailwind classes are spelled correctly
- Don't remove responsive classes (e.g., `md:`, `lg:` prefixes)
- Keep spacing classes to maintain layout

### Mobile Menu
If the mobile menu isn't working:
1. Verify Alpine.js is loading:
```html
<script defer src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js"></script>
```
2. Check that the menu button has the correct attributes:
```html
<button @click="isOpen = !isOpen" class="md:hidden p-2">
```

For additional help, consult the [Tailwind CSS documentation](https://tailwindcss.com/docs) or [Alpine.js documentation](https://alpinejs.dev/docs).