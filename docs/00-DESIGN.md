---
name: Indonesian Heritage Export
colors:
  surface: '#f8f9fa'
  surface-dim: '#d9dadb'
  surface-bright: '#f8f9fa'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f3f4f5'
  surface-container: '#edeeef'
  surface-container-high: '#e7e8e9'
  surface-container-highest: '#e1e3e4'
  on-surface: '#191c1d'
  on-surface-variant: '#414844'
  inverse-surface: '#2e3132'
  inverse-on-surface: '#f0f1f2'
  outline: '#717973'
  outline-variant: '#c1c8c2'
  surface-tint: '#3f6653'
  primary: '#012d1d'
  on-primary: '#ffffff'
  primary-container: '#1b4332'
  on-primary-container: '#86af99'
  inverse-primary: '#a5d0b9'
  secondary: '#7a590d'
  on-secondary: '#ffffff'
  secondary-container: '#fed17c'
  on-secondary-container: '#79580c'
  tertiary: '#322319'
  on-tertiary: '#ffffff'
  tertiary-container: '#4a382d'
  on-tertiary-container: '#baa193'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#c1ecd4'
  primary-fixed-dim: '#a5d0b9'
  on-primary-fixed: '#002114'
  on-primary-fixed-variant: '#274e3d'
  secondary-fixed: '#ffdea6'
  secondary-fixed-dim: '#ecc06d'
  on-secondary-fixed: '#271900'
  on-secondary-fixed-variant: '#5d4200'
  tertiary-fixed: '#f9ddce'
  tertiary-fixed-dim: '#dcc1b2'
  on-tertiary-fixed: '#27180f'
  on-tertiary-fixed-variant: '#554338'
  background: '#f8f9fa'
  on-background: '#191c1d'
  surface-variant: '#e1e3e4'
typography:
  display-lg:
    fontFamily: Urbanist
    fontSize: 48px
    fontWeight: '700'
    lineHeight: '1.1'
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Urbanist
    fontSize: 32px
    fontWeight: '600'
    lineHeight: '1.2'
  headline-lg-mobile:
    fontFamily: Urbanist
    fontSize: 28px
    fontWeight: '600'
    lineHeight: '1.2'
  headline-md:
    fontFamily: Urbanist
    fontSize: 24px
    fontWeight: '600'
    lineHeight: '1.3'
  body-lg:
    fontFamily: Urbanist
    fontSize: 18px
    fontWeight: '400'
    lineHeight: '1.6'
  body-md:
    fontFamily: Urbanist
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.6'
  label-md:
    fontFamily: Urbanist
    fontSize: 14px
    fontWeight: '500'
    lineHeight: '1.4'
    letterSpacing: 0.05em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  base: 8px
  section-gap-desktop: 120px
  section-gap-mobile: 64px
  grid-gutter: 24px
  container-max: 1280px
---

## Brand & Style

The brand personality is rooted in **Reliability, Premium Quality, and Indonesian Heritage**. This design system bridges the gap between industrial scale and agricultural warmth. It is designed to evoke a sense of "Global Excellence from Local Sources," targeting international B2B buyers who value supply chain stability and authentic food quality.

The visual style is **Corporate / Modern** with a lean toward **Minimalism**, presented in a crisp and professional **Light Mode**. By using clean, airy backgrounds and a structured layout, the focus remains on high-resolution product photography and certification credentials. The aesthetic is prestigious and trustworthy, ensuring that the "Arisyafood" commitment to hygiene and safety is reflected in a high-end, contemporary interface.

## Colors

The palette is derived directly from the agricultural landscape and the company's visual identity, optimized for a clean, high-clarity light environment.

*   **Primary (Deep Forest Green):** Represents the lush Indonesian landscape. In light mode, this serves as a strong, authoritative color for navigation, primary buttons, and brand headers.
*   **Secondary (Harvest Gold):** Inspired by the rice/grain element in the logo. It serves as a premium accent for call-to-actions, highlights, and icons, providing a warm contrast to the green.
*   **Tertiary (Earthy Brown):** A grounding color used for secondary UI elements, borders, or metadata, reflecting the organic nature of the products.
*   **Neutrals:** A range of soft whites and cool grays provide a professional, open backdrop, ensuring the interface feels breathable and modern.

## Typography

This design system uses **Urbanist** exclusively for headings, body copy, and technical UI elements. This creates a unified, sleek, and geometric experience that feels contemporary and premium. Its clean lines reflect the precision of modern food processing.

*   **Hierarchy:** Use bold weights for headlines to establish clear section breaks. 
*   **Scale:** On mobile, display sizes should compress slightly to avoid awkward line breaks, while body sizes remain constant for readability.
*   **Labels:** Technical specifications and logistics data utilize Urbanist with optimized spacing for functional clarity against the bright background.

## Layout & Spacing

The layout follows a **Fixed Grid** philosophy for the core container to maintain a high-end, editorial feel, while the internal elements use a fluid 12-column system.

*   **Grid:** 12 columns on desktop (1280px max), 6 columns on tablet, and 2 columns on mobile.
*   **Rhythm:** A strict 8px baseline grid is used. Section margins are generous (120px) to allow the "premium" nature of the products to breathe.
*   **Breakpoints:**
    *   Desktop: 1024px+
    *   Tablet: 768px - 1023px
    *   Mobile: < 767px

## Elevation & Depth

In this light-themed system, visual hierarchy is conveyed through **Tonal Layers** and subtle **Ambient Shadows**. Surfaces are defined by soft shifts in brightness and thin borders to maintain a clean, flat aesthetic.

*   **Surface Hierarchy:** The main background is the brightest layer. Cards and containers use a slightly darker neutral or a 1px Earthy Brown border at very low opacity to define boundaries.
*   **Depth:** Subtle, diffused shadows are used on primary floating elements (like dropdowns or active modal windows) to separate them from the base layout.
*   **Interactive Elements:** Use 1px borders for secondary actions. Interactive cards may gain a very soft shadow on hover to indicate they are "lifted" and clickable.

## Shapes

The design system employs a **Rounded (2)** roundedness profile. This choice emphasizes a modern, friendly, and high-quality feel, softening the industrial aspects of the brand while remaining professional.

*   **Primary Corners:** 8px (0.5rem) for standard components like tags, buttons, and inputs.
*   **Large Components:** 16px (1rem) for product cards and featured imagery containers.
*   **Buttons:** Standardized at 8px roundedness to provide a comfortable, tactile touch target.

## Components

### Buttons
*   **Primary:** Solid Primary Green (#1B4332) with white text. High contrast against light surfaces for maximum visibility.
*   **Secondary:** Solid Harvest Gold (#B0893C) with white text, used specifically for "Get a Quote" or "Inquire" actions.
*   **Outline:** 1px Primary Green border with transparent background for less urgent navigation.

### Cards
Product cards feature a 16px corner radius and a subtle 1px border or very light background tint. The product image should be centered to emphasize packaging quality.

### Inputs & Forms
Input fields use a 1px Earthy Brown border (#6C584C) at low opacity with an 8px corner radius. Labels use the same Urbanist `label-md` for a clean, professional data-entry experience.

### Certification Badges
A dedicated "Trust Row" component should house grayscale versions of Halal, HACCP, and ISO logos, which transition to full color on hover to emphasize compliance and reliability.

### Lists
Use custom bullet points in the shape of the logo's grain element or a simple Secondary Gold checkmark for "Why Choose Us" sections.