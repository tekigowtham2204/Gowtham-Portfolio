# Project Structure

```
Gowtham-Portfolio/
├── src/
│   ├── main.tsx                    # React entry point
│   ├── app/
│   │   ├── App.tsx                 # Main app component
│   │   └── components/
│   │       ├── Header.tsx          # Navigation
│   │       ├── HeroSection.tsx     # Hero intro
│   │       ├── AboutSection.tsx    # About me
│   │       ├── ProjectsSection.tsx # Projects showcase
│   │       ├── SkillsSection.tsx   # Technical skills
│   │       ├── ContactSection.tsx  # Contact info
│   │       ├── SmoothScrollProvider.tsx
│   │       ├── SectionHeading.tsx
│   │       └── ui/                 # Radix UI components (30+)
│   ├── assets/
│   └── styles/
│       ├── index.css
│       ├── tailwind.css
│       ├── theme.css
│       └── fonts.css
│
├── index.html                      # HTML template
├── package.json                    # Dependencies
├── vite.config.ts                  # Vite configuration
├── tsconfig.json                   # TypeScript config
├── postcss.config.mjs              # PostCSS config
└── .github/
    └── workflows/
        └── deploy.yml              # GitHub Pages CI/CD
```

## Key Features

- **Framework**: React 18.3.1 with TypeScript
- **Build Tool**: Vite 6.3.5
- **Styling**: Tailwind CSS 4.1 with @tailwindcss/vite
- **Components**: Radix UI primitives (30+ components)
- **Animations**: Framer Motion (motion/react)
- **Scroll**: Lenis for smooth scrolling
- **Icons**: Lucide React
- **Deployment**: GitHub Pages with GitHub Actions

## Component Hierarchy

```
App
├── SmoothScrollProvider (Lenis context)
│   ├── Header
│   ├── HeroSection
│   ├── AboutSection
│   ├── ProjectsSection
│   ├── SkillsSection
│   └── ContactSection
└── ToasterProvider (Sonner notifications)
```

## Development

```bash
npm install
npm run dev      # Start dev server on http://localhost:5173
npm run build    # Build for production
npm run preview  # Preview production build
```

## Deployment

Automatic deployment to GitHub Pages on push to `main` branch via `.github/workflows/deploy.yml`.

Live URL: `https://tekigowtham2204.github.io/Gowtham-Portfolio/`
