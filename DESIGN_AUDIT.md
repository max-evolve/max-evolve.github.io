# Design Audit: mayankkhera.com

**Date:** January 17, 2025  
**Auditor:** AI Design Review  
**Site Status:** Jekyll site using Minimal Mistakes theme (dirt skin)

**Design approach:** Keep as much as possible from the theme out of the box. Custom overrides have been removed so the site uses theme defaults for layout, footer, page titles, and typography.

---

## Executive Summary

Your site has a clean, minimal foundation with good content organization. However, there are several areas where design consistency, user experience, and visual polish can be significantly improved. The main issues center around inconsistent styling, accessibility concerns, and opportunities to better showcase your work.

**Overall Grade: B-** (Good foundation, needs refinement)

---

## 1. Visual Design & Aesthetics

### ✅ Strengths
- Clean, minimal aesthetic using Minimal Mistakes theme
- Good use of whitespace on most pages
- Professional color scheme (dirt skin theme)
- Nice hero image on homepage

### ⚠️ Issues & Recommendations

#### **1.1 Inconsistent Styling Approach**
**Problem:** Heavy use of inline styles mixed with theme styles creates inconsistency.

**Examples:**
- `about.md` uses extensive inline styles (`style="max-width: 750px; margin: 0 auto; padding: 2rem 1rem;"`)
- `readwise.md` uses inline link styles
- Theme CSS is being overridden with inline styles

**Impact:** 
- Harder to maintain
- Inconsistent appearance across pages
- Breaks responsive design principles
- Makes theme updates difficult

**Recommendation:**
- Move all inline styles to `assets/css/main.scss` or create custom SCSS partials
- Use CSS classes instead of inline styles
- Create reusable component classes (e.g., `.content-container`, `.highlight-box`)

#### **1.2 Typography Hierarchy**
**Problem:** Page titles are hidden globally (`page__title { display: none; }`), which hurts navigation and SEO.

**Current Code:**
```scss
.page__title, .archive__item-title {
  display: none;
}
```

**Impact:**
- Users can't see what page they're on
- Poor accessibility (screen readers rely on headings)
- SEO impact (missing H1 tags)

**Recommendation:**
- Remove or conditionally hide titles only where needed
- Use semantic HTML5 headings properly
- Consider showing titles on content pages but hiding on homepage

#### **1.3 Footer Completely Hidden**
**Problem:** Footer is hidden globally with `!important`, removing potential navigation and social links.

**Current Code:**
```scss
.page__footer {
  display: none !important;
}
```

**Recommendation:**
- Show footer on most pages (adds navigation options)
- Only hide on specific pages if needed
- Footer can include social links, copyright, etc.

#### **1.4 Color Consistency**
**Problem:** Hardcoded colors (`#007acc`, `#f9f9fb`, `#eee`) don't match theme variables.

**Recommendation:**
- Use theme color variables from `_sass/minimal-mistakes/_variables.scss`
- Create custom color variables for brand consistency
- Ensure colors work with theme's dark mode (if applicable)

---

## 2. User Experience & Navigation

### ✅ Strengths
- Clear navigation structure in `_data/navigation.yml`
- Logical content organization (Blogs, Resources, Readwise, About)
- Good use of collections (resources, books)

### ⚠️ Issues & Recommendations

#### **2.1 Homepage Content**
**Problem:** Homepage (`index.html`) is nearly empty - just a hero image with no content.

**Current State:**
- Only has hero image and author profile
- No introduction, featured content, or call-to-action
- Missed opportunity to engage visitors

**Recommendation:**
- Add a brief introduction/welcome message
- Feature 2-3 recent blog posts
- Add quick links to key resources
- Include a clear value proposition

#### **2.2 About Page Layout**
**Problem:** Image floats right, which can cause issues on mobile and creates awkward text flow.

**Current Code:**
```html
<img src="..." style="float: right; ...">
```

**Issues:**
- Float doesn't work well on mobile
- Text wrapping can be awkward
- Not accessible (no proper alt text context)

**Recommendation:**
- Use CSS Grid or Flexbox for responsive layout
- Stack image above text on mobile
- Consider using a more modern layout approach

#### **2.3 Link Styling Inconsistency**
**Problem:** Links use inline styles with hardcoded colors instead of theme styles.

**Recommendation:**
- Use theme's link styles
- Ensure hover states are defined
- Maintain consistent link appearance site-wide

#### **2.4 Missing Search Functionality**
**Problem:** Search is disabled in config (`search: false`).

**Recommendation:**
- Enable search for better UX (especially with growing content)
- Consider adding Algolia search (you have `jekyll-algolia` in plugins but it's not configured)

#### **2.5 Resources Page Structure**
**Problem:** Resources page uses plain markdown lists - could be more visually engaging.

**Recommendation:**
- Add icons or visual hierarchy
- Group related resources
- Add descriptions for each resource
- Consider card-based layout

---

## 3. Content Structure & Readability

### ✅ Strengths
- Well-organized content collections
- Good use of markdown
- Clear permalink structure

### ⚠️ Issues & Recommendations

#### **3.1 Missing Meta Information**
**Problem:** Some pages lack proper front matter (e.g., `resources.md` has empty title).

**Example:**
```yaml
title: " "  # Empty title
```

**Impact:**
- Poor SEO
- Missing page titles in browser tabs
- Accessibility issues

**Recommendation:**
- Add proper titles to all pages
- Include meta descriptions
- Add proper excerpts

#### **3.2 Readwise Page**
**Problem:** Very basic list presentation - could be more engaging.

**Current:**
- Simple bullet list
- No book covers or descriptions
- No filtering or categorization

**Recommendation:**
- Add book cover images
- Include short descriptions
- Add reading dates
- Consider categories or tags
- Add search/filter functionality

#### **3.3 Blog Post Formatting**
**Problem:** Posts lack visual hierarchy and engaging elements.

**Recommendation:**
- Add featured images to posts
- Improve typography hierarchy
- Add reading time estimates (currently disabled)
- Consider adding "related posts" section (currently enabled but verify it works)

#### **3.4 404 Page**
**Problem:** Very basic 404 page with no helpful navigation.

**Recommendation:**
- Add links to main sections
- Include search functionality
- Make it more helpful and branded

---

## 4. Responsive Design

### ⚠️ Issues & Recommendations

#### **4.1 Inline Styles Break Responsiveness**
**Problem:** Fixed widths and margins in inline styles don't adapt to screen sizes.

**Example:**
```html
<div style="max-width: 750px; margin: 0 auto; padding: 2rem 1rem;">
```

**Recommendation:**
- Use responsive units (rem, %, vw)
- Add media queries for mobile
- Test on multiple screen sizes

#### **4.2 Image Sizing**
**Problem:** Fixed image dimensions may not work well on all devices.

**Recommendation:**
- Use responsive images (`max-width: 100%; height: auto;`)
- Consider `srcset` for different resolutions
- Test image display on mobile

---

## 5. Accessibility

### ⚠️ Critical Issues

#### **5.1 Missing Alt Text Context**
**Problem:** Images may have alt text but context could be improved.

**Recommendation:**
- Ensure all images have descriptive alt text
- Test with screen readers
- Add ARIA labels where needed

#### **5.2 Hidden Content**
**Problem:** Hidden page titles hurt screen reader users.

**Recommendation:**
- Use `sr-only` class for visually hidden but accessible content
- Don't use `display: none` for important content

#### **5.3 Color Contrast**
**Problem:** Need to verify color contrast meets WCAG AA standards.

**Recommendation:**
- Test all text/background combinations
- Ensure minimum 4.5:1 contrast ratio
- Test with color blindness simulators

#### **5.4 Keyboard Navigation**
**Recommendation:**
- Test all interactive elements with keyboard
- Ensure focus states are visible
- Verify logical tab order

---

## 6. Performance

### ⚠️ Recommendations

#### **6.1 Image Optimization**
**Problem:** No evidence of image optimization.

**Recommendation:**
- Compress images (use tools like ImageOptim, TinyPNG)
- Use WebP format with fallbacks
- Implement lazy loading
- Add proper image dimensions to prevent layout shift

#### **6.2 Font Loading**
**Problem:** Loading multiple Google Fonts may impact performance.

**Current:**
```html
<link href="https://fonts.googleapis.com/css?family=Open+Sans:400,400i,700,700i|Merriweather:400,400i,700,700i|Inconsolata:400,700" rel="stylesheet">
```

**Recommendation:**
- Limit font weights/styles loaded
- Use `font-display: swap` for better performance
- Consider self-hosting fonts
- Preload critical fonts

#### **6.3 CSS Organization**
**Problem:** Custom styles mixed with theme styles.

**Recommendation:**
- Organize custom styles in separate partials
- Minimize CSS overrides
- Remove unused styles

---

## 7. Branding & Consistency

### ⚠️ Issues

#### **7.1 Inconsistent Styling**
**Problem:** Mix of inline styles, theme styles, and custom CSS creates inconsistency.

**Recommendation:**
- Establish design system/pattern library
- Document component usage
- Create style guide

#### **7.2 Social Links**
**Problem:** Social links in config but not visible (footer hidden).

**Recommendation:**
- Add social links to sidebar or header
- Ensure LinkedIn link works (you have `linkedin: mayankkhera`)

#### **7.3 Author Profile**
**Problem:** Author profile shown inconsistently across pages.

**Recommendation:**
- Standardize author profile display
- Ensure consistent avatar usage
- Add social proof/credentials

---

## 8. Specific Technical Issues

### **8.1 Typo in About Page**
**Issue:** "food deliver" should be "food delivery"

**Location:** `_pages/about.md` line 14

### **8.2 Empty Portfolio Page**
**Issue:** Portfolio page exists but is empty

**Recommendation:** Either add content or remove from navigation

### **8.3 Broken Links**
**Recommendation:** Verify all internal links work (e.g., `/resource-head-page/` vs `/resources/`)

### **8.4 Missing Favicon**
**Recommendation:** Add favicon for better branding

---

## Priority Recommendations

### 🔴 High Priority
1. **Remove inline styles** - Move to CSS classes
2. **Show page titles** - Fix accessibility and SEO
3. **Add homepage content** - Engage visitors immediately
4. **Fix responsive design** - Test and fix mobile layouts
5. **Enable search** - Improve navigation

### 🟡 Medium Priority
6. **Improve About page layout** - Better responsive design
7. **Enhance Readwise page** - Add images and descriptions
8. **Optimize images** - Improve performance
9. **Add social links** - Make them visible
10. **Improve 404 page** - Add helpful navigation

### 🟢 Low Priority
11. **Create style guide** - Document design system
12. **Add favicon** - Branding polish
13. **Enhance blog post formatting** - Better visual hierarchy
14. **Add meta descriptions** - SEO improvement

---

## Quick Wins

1. Fix typo: "food deliver" → "food delivery"
2. Add proper page titles to all pages
3. Remove `display: none` from page titles (or use `sr-only`)
4. Show footer on most pages
5. Add homepage introduction text
6. Enable search functionality

---

## Next Steps

1. **Review this audit** and prioritize fixes
2. **Create a design system** document
3. **Refactor inline styles** to CSS classes
4. **Test responsive design** on multiple devices
5. **Run accessibility audit** with tools like WAVE or axe
6. **Performance audit** with Lighthouse
7. **User testing** - Get feedback from real users

---

## Tools for Testing

- **Accessibility:** WAVE, axe DevTools, Lighthouse
- **Performance:** Lighthouse, PageSpeed Insights
- **Responsive:** Browser DevTools, Responsive Design Mode
- **Color Contrast:** WebAIM Contrast Checker
- **SEO:** Google Search Console, Screaming Frog

---

*This audit was conducted by reviewing code, configuration files, and site structure. For a complete assessment, visual inspection of the live site and user testing would be beneficial.*
