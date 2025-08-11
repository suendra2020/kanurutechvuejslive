# Kanuru Infosystems Vue.js Application

A modern, responsive single-page application built with Vue.js 3 and Bootstrap 5, converted from the original React application.

## Features

- **Modern Vue.js 3**: Built with the latest Vue.js 3 Composition API
- **Bootstrap 5**: Responsive design with Bootstrap 5 components and utilities
- **Single Page Application**: Smooth scrolling navigation between sections
- **Responsive Design**: Mobile-first approach with responsive layouts
- **Dynamic Content**: Animated text rotation and interactive elements
- **Professional Styling**: Gradient colors, hover effects, and modern UI design
- **Contact Form**: Functional contact form with Bootstrap styling
- **Service Showcase**: Comprehensive display of company services and features

## Sections

1. **Hero Section**: Welcome message with dynamic text rotation and company stats
2. **Services Section**: Core verticals with detailed service descriptions
3. **Features Section**: Why choose Kanuru Infosystems
4. **About Section**: Company information and expertise
5. **Contact Section**: Contact information and contact form
6. **Footer**: Copyright and legal links

## Technology Stack

- **Vue.js 3**: Progressive JavaScript framework
- **Vite**: Fast build tool and development server
- **Bootstrap 5**: CSS framework for responsive design
- **Bootstrap Icons**: Icon library for UI elements
- **CSS3**: Custom animations and styling

## Project Structure

```
kanuru-vue-project/
├── public/                 # Static assets
├── src/
│   ├── assets/            # Images and media files
│   ├── components/        # Vue components (if needed)
│   ├── App.vue           # Main application component
│   └── main.js           # Application entry point
├── dist/                  # Built application (production)
├── index.html            # HTML template
├── package.json          # Dependencies and scripts
├── vite.config.js        # Vite configuration
└── README.md             # This file
```

## Installation and Setup

### Prerequisites
- Node.js (version 16 or higher)
- npm or yarn package manager

### Installation Steps

1. **Clone or download the project**
   ```bash
   cd kanuru-vue-project
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start development server**
   ```bash
   npm run dev
   ```
   The application will be available at `http://localhost:3000`

4. **Build for production**
   ```bash
   npm run build
   ```
   The built files will be in the `dist/` directory

5. **Preview production build**
   ```bash
   npm run preview
   ```

## Available Scripts

- `npm run dev` - Start development server with hot reload
- `npm run build` - Build the application for production
- `npm run preview` - Preview the production build locally

## Customization

### Colors and Branding
The application uses a red-orange gradient theme that can be customized in the CSS:
- Primary gradient: `linear-gradient(135deg, #dc3545, #fd7e14)`
- You can modify colors in the `<style>` section of `index.html`

### Content Updates
- **Company Information**: Update text content in `src/App.vue`
- **Services**: Modify the `services` array in the Vue component
- **Images**: Replace images in `src/assets/` directory
- **Contact Information**: Update contact details in the contact section

### Adding New Sections
1. Add new section HTML in the `<template>` section of `App.vue`
2. Add corresponding data in the `setup()` function
3. Update navigation links if needed

## Responsive Design

The application is fully responsive and includes:
- Mobile-first design approach
- Bootstrap responsive grid system
- Responsive navigation with mobile menu
- Optimized images and layouts for all screen sizes

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Performance Features

- Optimized images (WebP format where supported)
- Minimal JavaScript bundle
- CSS optimization
- Fast loading with Vite

## Deployment

The built application in the `dist/` folder can be deployed to any static hosting service:
- Netlify
- Vercel
- GitHub Pages
- AWS S3
- Any web server

Simply upload the contents of the `dist/` folder to your hosting provider.

## License

This project is created for Kanuru Infosystems. All rights reserved.

## Support

For technical support or questions about this application, please contact the development team.

