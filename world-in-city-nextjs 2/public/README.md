# Public Assets

Place your images and static files here.

## Recommended Images to Add:

1. **Hero Background** - Full-screen background image for hero section
   - Size: 1920x1080px minimum
   - Name: `hero-background.jpg`

2. **City Images** - Images for each city card
   - `miami.jpg`
   - `dallas.jpg`
   - `new-york.jpg`
   - `los-angeles.jpg`
   - `atlanta.jpg`

3. **Creator Photo** - Photo for credibility section
   - Size: 800x1000px
   - Name: `kendall-hilton.jpg`

4. **Logo** (optional)
   - `logo.svg` or `logo.png`

5. **Favicon**
   - `favicon.ico`

## How to Use Images in Components

```tsx
// In any component
<img src="/hero-background.jpg" alt="Hero" />

// Or with Next.js Image (requires removing static export)
import Image from 'next/image'
<Image src="/hero-background.jpg" alt="Hero" width={1920} height={1080} />
```

## File Organization

```
public/
├── images/
│   ├── cities/
│   ├── backgrounds/
│   └── team/
└── videos/
```
