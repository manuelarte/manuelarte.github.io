# Manuel Doncel Martos Portfolio
My portfolio using [Astro](https://astro.build/) and [TailwindCSS](https://tailwindcss.com/). No JavaScript in final build.

> [NOTE!]
> Based on ..

## Deployed
Check out: [manuelarte.github.io](https://manuelarte.github.io)

## Tech Stack
- [Astro](https://astro.build/)
- [TailwindCSS](https://tailwindcss.com/)
- [Shiki](https://github.com/shikijs/shiki)

## Getting Started

```sh
# 1. Clone the repository
git clone https://github.com/devidevio/astro-developer-portfolio .

# 2. Install dependencies
npm install

# 3. Run the development server
npm run dev

# 4. Build for production
npm run build

# Deploy the contents of the `./dist` folder wherever you like.
```

## Customization
### Site & Domain Configuration
- Modify `astro.config.mjs` to update your `site` settings, including metadata for SEO.

### Theme Customization
- Adjust the primary theme color in `tailwind.config.js`, to fit your branding.

### Updating Content & SEO
Edit the **Frontmatter** variables in these files:
- `src/layouts/Layout.astro` – General page info (title, SEO, etc.)
- `src/components/Socials.astro` – Update your social media links.
- `src/components/Profile.astro` – Personal profile information.
- `src/components/ContentProjects.astro` – Projects/portfolio section content.
- `src/components/ContentAbout.astro` – About section content.

### Profile Picture
- Replace `/src/assets/profile.png` with your own image.

### Logo & OpenGraph Image
- Update these files:
  - `/public/img/logo.svg` (your logo)
  - `/public/img/meta.png` (your OpenGraph image)

Need a free OpenGraph image?
- https://tailwind-generator.com/og-image-generator/generator

### Sitemap & Robots.txt
- Adjust `/public/robots.txt` to match your domain.

## ⭐ Contributing
Feel free to fork, customize, and contribute to this project. If you find it useful, leaving a star would be greatly appreciated.
