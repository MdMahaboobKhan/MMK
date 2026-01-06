# Mohammed Mahaboob Khan - Portfolio Website

A modern, responsive portfolio website showcasing my professional experience, technical projects, skills, and achievements.

🔗 **Live Demo**: [Your Portfolio URL]

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Sections Overview](#sections-overview)
- [CSS Classes Reference](#css-classes-reference)
- [JavaScript Modules](#javascript-modules)
- [Setup & Installation](#setup--installation)
- [Customization Guide](#customization-guide)
- [Browser Support](#browser-support)
- [License](#license)

## ✨ Features

- **Responsive Design**: Fully responsive layout that works on desktop, tablet, and mobile devices
- **Modern UI/UX**: Clean, professional design with smooth animations and transitions
- **Interactive Particle Effect**: Dynamic particle background on the home page
- **Project Filtering**: Isotope.js powered filtering for projects and skills
- **Smooth Scrolling**: jQuery-based smooth scrolling navigation
- **Custom Theming**: Purple gradient theme with carefully chosen color schemes
- **Optimized Performance**: Separated CSS and JavaScript for better caching and performance

## 🛠 Tech Stack

### Frontend
- **HTML5**: Semantic markup
- **CSS3**: Custom styling with gradients, animations, and transitions
- **JavaScript (ES6)**: Modern JavaScript features
- **jQuery**: DOM manipulation and animations

### Libraries & Frameworks
- **Bootstrap 4**: Responsive grid system and components
- **Isotope.js**: Filtering and sorting layouts
- **Font Awesome 4.7**: Icon library
- **jQuery Easing**: Smooth scroll animations
- **Parallaxie.js**: Parallax effects
- **ImagesLoaded**: Image loading utility

## 📁 Project Structure

```
MMK/
├── index.html              # Main HTML file
├── README.md              # Project documentation
├── style.css              # Base styles
├── css/
│   ├── custom.css         # Custom theme and component styles
│   ├── responsive.css     # Responsive design rules
│   └── icons.css          # Icon fonts
├── js/
│   ├── custom.js          # Main JavaScript functionality
│   ├── particles.js       # Particle effect for home page
│   ├── portfolio.js       # Portfolio grid functionality
│   ├── all.js             # Bundled libraries
│   ├── headline.js        # Animated headline
│   ├── parallaxie.js      # Parallax effects
│   └── contact_me.js      # Contact form handler
├── images/                # Image assets
└── fonts/                 # Custom fonts
```

## 📄 Sections Overview

### 1. Home (Hero Section)
- **ID**: `#home`
- **Features**:
  - Animated particle background
  - Gradient overlay
  - Rotating text showcasing career highlights
  - Call-to-action buttons
- **Classes**: `.main-banner`, `.heading`, `.home-info`, `.home-buttons`

### 2. About Me
- **ID**: `#about`
- **Features**:
  - Professional summary
  - Social media links (LinkedIn, GitHub, Google Play)
  - Profile photo
- **Classes**: `.message-box`, `.img-fluid`

### 3. Technical Projects
- **ID**: `#services`
- **Features**:
  - Filterable project grid (All, Android Apps, Web Apps, ML/AI)
  - Project cards with hover effects
  - External links to GitHub and Play Store
- **Classes**: `.services-inner-box`, `.gallery-menu-projects`, `.gallery-list-projects`
- **Filter Classes**: `.proj_ml`, `.proj_android`, `.proj_web`

### 4. Technical Skills
- **ID**: `#portfolio`
- **Features**:
  - Categorized skills (Programming, Databases, Courses, Others)
  - Filterable grid layout
  - Card-based presentation
- **Classes**: `.gallery-menu`, `.gallery-list`
- **Filter Classes**: `.gal_a`, `.gal_b`, `.gal_c`, `.gal_d`

### 5. Professional Experience
- **ID**: `#testimonials`
- **Features**:
  - Timeline of work experience
  - Detailed bullet points for each role
  - Companies: Goldman Sachs, Aires Medical, WorkSpan, Siemens Gamesa
- **Classes**: `.testimonial`, `.desc`

### 6. Additional Activities
- **ID**: `#blog`
- **Features**:
  - Achievements and extracurricular activities
  - Event management, sports, academic groups
- **Classes**: `.post-box`, `.post-info`, `.post-padding`

## 🎨 CSS Classes Reference

### Layout Classes

| Class | Purpose | Usage |
|-------|---------|-------|
| `.section` | Main section container | Applied to all major sections |
| `.wb` | White background | Used for light sections |
| `.lb` | Light background | Alternative light background |
| `.container` | Bootstrap container | Wraps section content |

### Component Classes

#### Cards
```css
.services-inner-box {
    /* Enhanced card styling */
    background: rgba(255, 255, 255, 0.95);
    border-radius: 15px;
    padding: 30px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
}
```

#### Buttons
```css
.button-group button {
    /* Filter button styling */
    background: rgba(255, 255, 255, 0.2);
    border: 2px solid #fff;
    border-radius: 25px;
}
```

#### Utilities
- `.text-justify`: Text alignment justify
- `.post-padding`: Adds 20px top padding to post info boxes

### Theme-Specific Classes

#### Gradient Backgrounds
```css
#services.section {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

#portfolio.section {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

#blog.section {
    background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
}
```

#### Card Heights
- **Technical Projects**: `420px` (ID: `#services .services-inner-box`)
- **Technical Skills**: `400px` (ID: `#portfolio .services-inner-box`)

### Animation Classes

```css
@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

@keyframes fadeInUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
}

@keyframes gradientShift {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}
```

## 🔧 JavaScript Modules

### 1. particles.js
**Purpose**: Creates interactive particle effect on home page

**Features**:
- 80 floating particles
- Dynamic connections between nearby particles
- Responsive canvas sizing
- Smooth 60fps animations

**Key Variables**:
```javascript
particleCount: 80           // Number of particles
speedX/speedY: ±0.5        // Particle velocity
connectionDistance: 100     // Distance for particle connections
```

### 2. custom.js
**Purpose**: Main functionality and interactions

**Key Features**:
- **Smooth Scrolling**: jQuery easing for anchor links
- **Navbar Behavior**: Shrink on scroll, hide on modal
- **Scroll to Top**: Back-to-top button
- **Gallery Filtering**: Separate isotope instances for:
  - Skills (`.gallery-menu` → `.gallery-list`)
  - Projects (`.gallery-menu-projects` → `.gallery-list-projects`)
- **Fun Facts Counter**: Animated number counting

**Filter Setup**:
```javascript
// Skills Filter
var $grid = $('.gallery-list').isotope({
    itemSelector: '.gallery-grid'
});

// Projects Filter
var $gridProjects = $('.gallery-list-projects').isotope({
    itemSelector: '.gallery-grid'
});
```

### 3. portfolio.js
**Purpose**: Portfolio grid layout management

**Features**:
- Responsive column calculation
- Masonry layout with Isotope
- Dynamic item sizing

## 🚀 Setup & Installation

### Prerequisites
- A modern web browser
- A local web server (optional, for testing)

### Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/MdMahaboobKhan/MMK.git
   cd MMK
   ```

2. **Open in browser**
   ```bash
   # Open index.html directly in your browser, or
   # Use a local server (recommended)
   python -m http.server 8000
   # Then navigate to http://localhost:8000
   ```

3. **Customize**
   - Edit `index.html` for content changes
   - Modify `css/custom.css` for styling
   - Update `js/custom.js` for functionality changes

## 🎨 Customization Guide

### Changing Colors

The main theme colors are defined in `css/custom.css`:

```css
/* Primary Gradient */
#services.section, #portfolio.section {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

/* Accent Colors */
.services-inner-box h2 {
    color: #667eea;  /* Primary purple */
}

.services-inner-box h2 a:hover {
    color: #764ba2;  /* Secondary purple */
}
```

### Updating Content

1. **Personal Information**: Edit `index.html` lines 89-93
2. **Projects**: Edit `index.html` lines 148-235
3. **Skills**: Edit `index.html` lines 269-357
4. **Experience**: Edit `index.html` lines 375-423

### Adding New Projects

1. Add a new project card in the appropriate section
2. Apply filter class: `.proj_ml`, `.proj_android`, or `.proj_web`
3. Follow the existing structure:

```html
<div class="col-md-4 gallery-grid proj_ml">
    <div class="services-inner-box">
        <h2><a href="GITHUB_URL" target="_blank">Project Name</a></h2>
        <p class="text-justify">Description here</p>
        <p><b>Technologies:</b> Tech stack</p>
        <p><b>Concepts:</b> Key concepts</p>
    </div>
</div>
```

## 🌐 Browser Support

- ✅ Chrome (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ✅ Edge (latest)
- ✅ Opera (latest)

## 📱 Responsive Breakpoints

- **Desktop**: > 1200px
- **Tablet**: 768px - 1199px
- **Mobile**: < 767px

## ⚡ Performance Optimizations

- **CSS/JS Separation**: Styles and scripts in external files for better caching
- **Minified Libraries**: Production-ready library versions
- **Image Optimization**: Properly sized images
- **Lazy Loading**: Images loaded as needed
- **Efficient Animations**: CSS animations over JavaScript where possible

## 🤝 Contributing

This is a personal portfolio project, but suggestions and feedback are welcome!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📧 Contact

**Mohammed Mahaboob Khan**
- LinkedIn: [linkedin.com/in/mohammed-mahaboob-khan-570615144](https://www.linkedin.com/in/mohammed-mahaboob-khan-570615144/)
- GitHub: [@MdMahaboobKhan](https://github.com/MdMahaboobKhan)
- Google Play: [Developer Profile](https://play.google.com/store/apps/developer?id=Mohammed+Mahaboob+Khan&hl=en_US)

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

⭐ **If you found this portfolio helpful, please consider giving it a star!**

Built with ❤️ by Mohammed Mahaboob Khan
