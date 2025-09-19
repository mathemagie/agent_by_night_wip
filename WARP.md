# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a work-in-progress (WIP) version of the Agent by Night project - a Vercel HTML starter template focused on static web deployment with edge computing capabilities. This repository serves as an experimental/development space for features that will eventually be integrated into the main `agent_by_night` project.

Based on the main project architecture, this WIP version will feature a high-performance multilingual HTML template with Vercel Edge Middleware for security headers, interactive p5.js particle animations, and analytics integration.

## Expected Architecture

The project follows a static-first architecture optimized for Vercel deployment:

- **Static HTML**: Single `index.html` file serves as the main application entry point
- **Edge Middleware**: `middleware.js` implements Vercel Edge Middleware for comprehensive security headers
- **Interactive Animation**: p5.js-based particle system with advanced mobile sensor integration
- **Multilingual Support**: Built-in French/English language switching with SEO optimization
- **Theme System**: Dynamic dark/light theme switching with auto-cycling capabilities
- **Vercel Integration**: Zero-configuration deployment with analytics and CDN distribution

### Core Files Structure

```
project-root/
├── index.html              # Main HTML template with p5.js integration
├── css/
│   └── styles.css          # Organized CSS with theme variables
├── js/
│   └── script.js           # Interactive particle animation engine
├── middleware.js           # Vercel Edge Middleware for security headers
├── package.json            # Dependencies and linting scripts
├── manifest.json           # PWA manifest for mobile app-like behavior
└── eslint.config.js        # ESLint configuration
```

## Development Commands

This project uses Vercel's platform for development and deployment, with additional linting tools:

### Local Development
- **Start development server**: `vercel dev`
- **Install dependencies**: `npm install`

### Code Quality
- **Run all lints**: `npm run lint`
- **Lint JavaScript only**: `npm run lint:js`
- **Lint CSS only**: `npm run lint:css`
- **Auto-fix linting issues**: `npm run lint:fix`
- **Auto-fix JS issues**: `npm run lint:js:fix`
- **Auto-fix CSS issues**: `npm run lint:css:fix`

### Deployment
- **Production deployment**: `vercel --prod`
- **Preview deployment**: Automatic on pull requests
- **Automatic deployment**: Triggered on `git push` to main branch

## Technical Architecture Details

### Vercel Edge Middleware
The `middleware.js` file runs at the edge before caching and implements:
- **Security Headers**: CSP, HSTS, X-Frame-Options, X-Content-Type-Options
- **Language Routing**: Based on URL parameters or Accept-Language header
- **SEO Optimization**: Content-Language and Vary headers for multilingual support

### P5.js Interactive Animation System
The animation engine features:
- **Particle System**: 280+ particles with dynamic connections and physics
- **Mobile Sensors**: Device orientation and acceleration integration for mobile devices
- **Multi-touch Support**: Pinch to zoom, 3-finger tap for explosion effects
- **Theme Cycling**: Automatic theme transitions with smooth color interpolation
- **Heartbeat Effects**: Pulsing animations synchronized to configurable BPM
- **Performance Optimization**: Efficient rendering with spatial partitioning

### Dependencies
```json
{
  "dependencies": {
    "@vercel/edge": "^0.1.2"
  },
  "devDependencies": {
    "eslint": "^8.57.0",
    "@eslint/js": "^8.57.0",
    "stylelint": "^16.2.0",
    "stylelint-config-standard": "^35.0.0"
  }
}
```

## Development Guidelines

### Code Organization
- Keep HTML structure clean and semantic
- Organize CSS with logical component sections and theme variables
- Group related JavaScript functions and maintain clear separation of concerns
- Use ES6 modules and modern JavaScript features
- Follow the existing naming conventions (camelCase for JS, kebab-case for CSS)

### Mobile-First Approach
- Test interactive features on both desktop and mobile devices
- Ensure sensor integration works properly on iOS and Android
- Verify fullscreen capabilities and responsive design
- Test multi-touch gestures and device orientation changes

### Performance Considerations
- Monitor particle count and rendering performance
- Optimize animation loops and avoid unnecessary calculations
- Use efficient event handling for touch and mouse interactions
- Leverage Vercel's edge network and caching capabilities

### Security and SEO
- Maintain comprehensive security headers through middleware
- Implement proper language detection and routing
- Use semantic HTML structure for accessibility
- Test analytics integration and privacy compliance

## Key Features to Implement

### Multilingual Support
- URL parameter-based language switching (`?lang=en` or `?lang=fr`)
- Browser language detection via Accept-Language header
- SEO-optimized language headers and meta tags

### Theme System
- Dynamic theme switching with localStorage persistence
- Auto-cycling themes with configurable intervals
- Smooth color transitions between themes
- Support for custom theme definitions

### Interactive Effects
- Mouse/touch attraction and repulsion forces
- Ripple effects on click/tap
- Mobile sensor integration (tilt, shake, acceleration)
- Fullscreen mode with proper canvas resizing

## Testing and Quality Assurance

Before deploying changes:
1. Run `npm run lint` to ensure code quality
2. Test `vercel dev` locally with different screen sizes
3. Verify mobile sensor functionality on actual devices
4. Check both French and English language switching
5. Test theme transitions and interactive particle effects
6. Validate security headers in browser developer tools