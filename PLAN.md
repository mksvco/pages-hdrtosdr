# Create One-Page Static Website for HDR→SDR App

## Overview

Create a modern, single-page static website that showcases the HDR→SDR macOS application. The website will feature a dark theme matching the app's aesthetic with red accent colors, comprehensive descriptions, feature highlights, and a prominent Mac App Store download button.

## Files to Create

### 1. `index.html` (root directory)

Main HTML structure with semantic sections:

- Header with app title and tagline
- Hero section with main description
- Features section with detailed write-ups (including 3 feature images: feature-quicktime-matching.jpg, feature-tone-mapping.jpg, feature-app-interface.jpg)
- Call-to-action section with Mac App Store button
- Footer

### 2. `styles.css` (root directory)

Comprehensive CSS matching the app's exact visual style with detailed descriptions:

## Content Write-Ups

### Hero Section Title & Tagline

**Title**: HDR→SDR

**Tagline**: Convert iPhone HDR footage to SDR with QuickTime-matching quality

### Main Description

Transform your iPhone HDR videos into beautifully tone-mapped SDR files that match QuickTime's look. Built for macOS, HDR→SDR uses Apple's AVFoundation color pipeline to deliver professional-grade conversions with precise color accuracy.

Whether you're editing in Final Cut Pro, sharing on social media, or archiving your footage, HDR→SDR ensures your videos look exactly as they do when played in QuickTime—no surprises, no color shifts, just consistent, reliable results.

### Features Section Write-Ups

#### Feature 1: QuickTime-Matching Quality

![QuickTime Matching](feature-quicktime-matching.jpg)

HDR→SDR uses Apple's native AVFoundation tone mapping pipeline to replicate QuickTime's HDR→SDR conversion. By requesting Rec.709 output at the reader stage and writing explicit Rec.709 tags at the writer stage, the app delivers pixel-perfect parity with QuickTime's look. No custom tone curves, no guesswork—just the same color science Apple uses.

*Image: feature-quicktime-matching.jpg (1000x1000, will be rescaled to fit in grid)*

#### Feature 2: Professional Output Formats

Choose from multiple professional-grade output formats to suit your workflow. Export to ProRes 422 for maximum quality and editing flexibility, or use H.264 or HEVC for smaller file sizes and broader compatibility. All outputs are properly tagged with Rec.709 color space metadata for consistent playback across all applications.

#### Feature 3: Advanced Tone Mapping Control

Fine-tune your conversions with seven built-in tone mapping presets: Natural, Bright, Cinematic, Vivid, Soft, High Contrast, and Preserve Highlights. For ultimate control, use the Custom preset to adjust highlight rolloff, shadow lift, and exposure with precision sliders. Each preset is carefully tuned to deliver specific looks while maintaining color accuracy.

#### Feature 4: Batch Processing Made Simple

Drag and drop multiple HDR videos into the app and process them all in one go. The intuitive queue system shows progress for each file, lets you reorder items, and provides clear status indicators. Start your conversion, and the app handles the rest—you'll get a notification when everything is complete.

#### Feature 5: Beautiful, Native macOS Experience

![App Interface](feature-app-interface.jpg)

Built with SwiftUI and designed specifically for macOS, HDR→SDR feels right at home on your Mac. The dark, elegant interface features smooth animations, glowing progress indicators, and a streamlined workflow that gets out of your way. No complex settings, no confusing options—just drag, drop, and convert.

*Image: feature-app-interface.jpg (1000x1000, will be rescaled to fit in grid)*

#### Feature 6: Intelligent HDR Detection

The app automatically detects whether your footage is actually HDR by inspecting video track metadata, transfer functions, and color primaries. If a file isn't HDR, you'll see a helpful warning so you can avoid unnecessary conversions. This saves time and ensures you're only processing files that need conversion.

### Technical Details Section

**System Requirements**: macOS 14.0 or later

**Output Formats**: ProRes 422 Rec.709 (.mov), H.264 Rec.709 (.mp4), HEVC Rec.709 (.mp4)

**Color Space**: Rec.709 (SDR)

**Tone Mapping**: AVFoundation native pipeline with optional custom adjustments

### Call-to-Action Section

**Heading**: Ready to Convert Your HDR Footage?

**Subheading**: Download HDR→SDR from the Mac App Store and start converting your videos today.

**Mac App Store Button**:

- Placeholder URL: `https://apps.apple.com/app/hdr-to-sdr/id[APP_ID]`
- Standard Mac App Store badge/button styling
- Opens in new tab

### Footer

Made by Mike Savoie

[Visit mksv.co](https://mksv.co)

## Design Specifications

### Color Palette (Matching App Exactly)

- Background Base: Near black (#000000 or rgba(0, 0, 0, 1))
- Frosted Glass Overlay: rgba(0, 0, 0, 0.3) - dark overlay on top of ultra-thin material
- Text Primary: #FFFFFF (white)
- Text Secondary: rgba(255, 255, 255, 0.85) - 85% opacity white
- Accent Red: rgb(255, 26, 26) / #FF1A1A - primary red accent (rgb(1.0, 0.10, 0.10))
- Rim Light Red: rgb(255, 97, 97) / #FF6161 - neon-ish red for rim lighting (rgb(1.0, 0.38, 0.38))
- Border/Divider: rgba(255, 255, 255, 0.1)

### Typography

- Headings: System font stack (San Francisco on macOS), bold weights
- Body: System font stack, regular weight
- Monospace: For technical details (code snippets, version numbers)

### Layout

- Max content width: 1200px
- Padding: Responsive (24px mobile, 48px desktop)
- Section spacing: 80px between major sections
- Card-based feature layout with subtle shadows and borders

### Responsive Breakpoints

- Mobile: < 768px (stacked layout, full-width cards)
- Tablet: 768px - 1024px (2-column feature grid)
- Desktop: > 1024px (3-column feature grid, optimal spacing)

## Implementation Details

1. **HTML Structure**: Semantic HTML5 with proper heading hierarchy (h1 for title, h2 for section headings, h3 for feature titles)

2. **CSS Architecture with Detailed Styling Descriptions**:

**Frosted Glass Effect (Matching App's Ultra-Thin Material)**:

   - Use `backdrop-filter: blur(20px) saturate(180%)` to create the frosted glass effect
   - Apply `background: rgba(255, 255, 255, 0.05)` for the ultra-thin material base
   - Add dark overlay: `background: rgba(0, 0, 0, 0.3)` on top to match app's tint
   - Use `::before` or layered backgrounds to stack the effects
   - Example structure:
     ```css
     .frosted-glass {
       background: rgba(255, 255, 255, 0.05);
       backdrop-filter: blur(20px) saturate(180%);
       position: relative;
     }
     .frosted-glass::after {
       content: '';
       position: absolute;
       inset: 0;
       background: rgba(0, 0, 0, 0.3);
       pointer-events: none;
     }
     ```


**Rim Lighting Effect (Angular Gradient Border)**:

   - Create animated rotating border using `conic-gradient` or `angular-gradient`
   - Use rim light red (#FF6161) with opacity stops: clear → 0.85 opacity → clear
   - Animate rotation with `@keyframes` and `transform: rotate()`
   - Apply multiple shadow layers for glow:
     - `box-shadow: 0 0 18px rgba(255, 97, 97, 0.95)` (close glow)
     - `box-shadow: 0 0 36px rgba(255, 97, 97, 0.55)` (far glow)
   - Use `blend-mode: screen` for additive blending effect
   - Border radius: 18px to match app's rounded corners
   - Example:
     ```css
     .rim-light-border {
       border: 2px solid transparent;
       border-radius: 18px;
       background: conic-gradient(from 0deg, 
         transparent 0deg,
         rgba(255, 97, 97, 0) 6%,
         rgba(255, 97, 97, 0.85) 14%,
         rgba(255, 97, 97, 0) 22%,
         transparent 50%,
         rgba(255, 97, 97, 0) 56%,
         rgba(255, 97, 97, 0.65) 64%,
         rgba(255, 97, 97, 0) 72%,
         transparent 100%);
       animation: rimRotate 2.4s linear infinite;
       box-shadow: 
         0 0 18px rgba(255, 97, 97, 0.95),
         0 0 36px rgba(255, 97, 97, 0.55);
     }
     @keyframes rimRotate {
       from { transform: rotate(0deg); }
       to { transform: rotate(360deg); }
     }
     ```


**Red Glow Effects**:

   - Primary accent red (#FF1A1A) for main elements
   - Multiple shadow layers for depth:
     - Close shadow: `0 0 8px rgba(255, 26, 26, 0.35)`
     - Medium shadow: `0 0 18px rgba(255, 26, 26, 0.95)` (when pulsing)
     - Far shadow: `0 0 36px rgba(255, 26, 26, 0.55)` (when pulsing)
   - Pulse animation that toggles between two glow intensities
   - Use `opacity` transitions for smooth pulsing
   - Example:
     ```css
     .glow-pulse {
       box-shadow: 
         0 0 8px rgba(255, 26, 26, 0.35),
         0 0 14px rgba(255, 26, 26, 0.20);
       animation: glowPulse 2.2s ease-in-out infinite;
     }
     @keyframes glowPulse {
       0%, 100% { 
         box-shadow: 
           0 0 8px rgba(255, 26, 26, 0.35),
           0 0 14px rgba(255, 26, 26, 0.20);
       }
       50% {
         box-shadow: 
           0 0 18px rgba(255, 26, 26, 0.95),
           0 0 36px rgba(255, 26, 26, 0.55);
       }
     }
     ```


**Card/Section Styling**:

   - Rounded corners: `border-radius: 18px` (matching app)
   - Frosted glass background with dark overlay
   - Red border: `border: 2px solid #FF1A1A` with glow shadow
   - Optional rim light border overlay for special elements
   - Padding: 18px-20px to match app spacing

**Feature Image Styling**:

   - Images are 1000x1000 pixels source size, rescaled to fit within the feature card grid
   - Use `width: 100%` and `height: auto` for responsive scaling
   - Maintain aspect ratio: `object-fit: cover` or `object-fit: contain` depending on desired effect
   - Rounded corners matching cards: `border-radius: 18px` (or slightly less, e.g., 16px)
   - Optional subtle border: `border: 1px solid rgba(255, 255, 255, 0.1)`
   - Subtle shadow for depth: `box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3)`
   - Smooth transitions on hover: `transition: transform 0.3s ease-in-out`
   - Optional hover effect: slight scale up `transform: scale(1.02)` with increased shadow
   - Place images at the top of feature cards, before the text content
   - Example:
     ```css
     .feature-image {
       width: 100%;
       height: auto;
       border-radius: 16px;
       object-fit: cover;
       border: 1px solid rgba(255, 255, 255, 0.1);
       box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
       transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
     }
     .feature-image:hover {
       transform: scale(1.02);
       box-shadow: 0 8px 24px rgba(0, 0, 0, 0.4);
     }
     ```


**Button Styling (Mac App Store Button)**:

   - Large, prominent button with red accent (#FF1A1A)
   - Rounded corners: `border-radius: 12px` (slightly less than cards)
   - Frosted glass effect with red tint
   - Hover state: increased glow intensity
   - Active state: slight scale down (0.98)
   - Smooth transitions: `transition: all 0.3s ease-in-out`
   - Minimum height: 44px for touch targets

**Typography**:

   - System font stack: `-apple-system, BlinkMacSystemFont, "SF Pro Display", "SF Pro Text", system-ui, sans-serif`
   - Headings: Bold weights (600-700)
   - Body: Regular weight (400)
   - Monospace for technical details: `"SF Mono", "Monaco", "Menlo", monospace`
   - Line heights: 1.4-1.6 for readability

**Layout & Spacing**:

   - CSS custom properties for consistent spacing:
     ```css
     :root {
       --spacing-xs: 8px;
       --spacing-sm: 12px;
       --spacing-md: 18px;
       --spacing-lg: 24px;
       --spacing-xl: 48px;
       --spacing-xxl: 80px;
       --border-radius: 18px;
       --border-radius-sm: 12px;
     }
     ```

   - Max content width: 1200px, centered
   - Section spacing: 80px between major sections
   - Mobile-first responsive design with Flexbox/Grid

**Animations & Transitions**:

   - Smooth scroll: `scroll-behavior: smooth`
   - Fade-in animations for sections on scroll (optional)
   - Hover transitions: `transition: all 0.3s ease-in-out`
   - Button press feedback: `transform: scale(0.98)` on active
   - Rim light rotation: `animation: rimRotate 2.4s linear infinite`
   - Glow pulse: `animation: glowPulse 2.2s ease-in-out infinite`

**Responsive Design**:

   - Mobile-first approach
   - Breakpoints: 768px (tablet), 1024px (desktop)
   - Flexible grid: 1 column (mobile) → 2 columns (tablet) → 3 columns (desktop)
   - Responsive typography: clamp() for fluid font sizes
   - Padding adjustments: 24px (mobile) → 48px (desktop)

3. **Mac App Store Button**:

   - Use official Apple-provided badge assets or create a styled button matching Apple's guidelines
   - Include hover state
   - Ensure proper accessibility (alt text, ARIA labels)

4. **Performance**:

   - Minimal dependencies (no frameworks)
   - Optimized images if any screenshots are added later
   - Fast loading with inline critical CSS

5. **Accessibility**:

   - Proper heading structure
   - Alt text for images
   - Sufficient color contrast
   - Keyboard navigation support
   - ARIA labels where appropriate

## File Structure

```
hdr-to-sdr-app/
├── index.html
├── styles.css
├── feature-quicktime-matching.jpg (1000x1000, placeholder)
├── feature-tone-mapping.jpg (1000x1000, placeholder)
└── feature-app-interface.jpg (1000x1000, placeholder)
```

The website files will be placed in the project root directory. Three feature images (1000x1000 pixels each) will be included as placeholders:

- `feature-quicktime-matching.jpg` - for Feature 1 (QuickTime-Matching Quality)
- `feature-tone-mapping.jpg` - for Feature 3 (Advanced Tone Mapping Control)
- `feature-app-interface.jpg` - for Feature 5 (Beautiful, Native macOS Experience)

Images will be rescaled responsively to fit within the feature card grid layout. The website will be completely self-contained with no external dependencies, making it easy to host on any static hosting service (GitHub Pages, Netlify, Vercel, etc.).