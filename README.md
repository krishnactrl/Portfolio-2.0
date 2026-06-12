# Atharva Shyam Samrat — Portfolio

A minimal, fast, responsive React portfolio site with dark/light mode, scroll animations, and project showcase.

## 🚀 Getting Started

### Prerequisites
- Node.js v16+ (https://nodejs.org)
- npm (comes with Node.js)

### Installation & Run

```bash
# 1. Navigate into the project folder
cd portfolio

# 2. Install dependencies
npm install

# 3. Start development server
npm start
```

The site opens at **http://localhost:3000**

### Production Build

```bash
npm run build
```

Output goes to the `build/` folder — deploy to Netlify, Vercel, or GitHub Pages.

---

## 📁 Project Structure

```
portfolio/
├── public/
│   └── index.html          # HTML shell + Google Fonts
├── src/
│   ├── components/
│   │   ├── Navbar.jsx       # Fixed nav with dark/light toggle + mobile menu
│   │   ├── Navbar.css
│   │   ├── Hero.jsx         # Typing animation, CTA buttons, code card
│   │   ├── Hero.css
│   │   ├── About.jsx        # Bio, stats, interests grid
│   │   ├── About.css
│   │   ├── Skills.jsx       # Tabbed skill bars + tag cloud
│   │   ├── Skills.css
│   │   ├── Projects.jsx     # Project cards with hover animations
│   │   ├── Projects.css
│   │   ├── Resume.jsx       # Education/experience timeline + download button
│   │   ├── Resume.css
│   │   ├── Contact.jsx      # Form with validation + social links
│   │   ├── Contact.css
│   │   ├── Footer.jsx
│   │   └── Footer.css
│   ├── data/
│   │   └── portfolioData.js # ← All content lives here. Edit this file.
│   ├── hooks/
│   │   └── useScrollReveal.js  # IntersectionObserver fade-in hook
│   ├── styles/
│   │   └── global.css       # CSS variables, theming, utilities
│   ├── App.js               # Root: theme state, layout
│   └── index.js             # React DOM entry
└── package.json
```

---

## 🎨 Customisation

### Update Your Content
All personal data is in one file: **`src/data/portfolioData.js`**

Change:
- `personalInfo` — name, email, GitHub, LinkedIn, typing roles, about text
- `education` — add/edit degrees
- `experience` — internships and jobs
- `certificates` — certs you've earned
- `skills` — skill names + proficiency levels (0–100)
- `projects` — your actual projects (title, description, tech, links)

### Add Your Resume PDF
Place your resume PDF at `public/resume.pdf`.  
The download button in the Resume section will automatically serve it.

### Dark / Light Mode
- Toggle button is in the Navbar (☀️ / 🌙)
- Theme preference is stored in `localStorage` under key `portfolio-theme`
- CSS variables are in `src/styles/global.css` under `:root` (dark) and `[data-theme="light"]`

### Connect the Contact Form
The form currently logs to console. To make it actually send emails:

**Option A — Formspree (free, no backend needed)**
```js
// In Contact.jsx handleSubmit:
await fetch("https://formspree.io/f/YOUR_FORM_ID", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify(form),
});
```

**Option B — EmailJS**
```bash
npm install emailjs-com
```
Then use `emailjs.sendForm(...)` in the submit handler.

---

## 🌐 Deployment

### Vercel (recommended — free)
```bash
npm install -g vercel
vercel
```

### Netlify
Drag and drop the `build/` folder at https://app.netlify.com

### GitHub Pages
```bash
npm install gh-pages --save-dev
# In package.json add:
# "homepage": "https://Atharvasamrat.github.io/portfolio"
# "predeploy": "npm run build"
# "deploy": "gh-pages -d build"
npm run deploy
```

---

## ✨ Features

| Feature | Implementation |
|---|---|
| Dark / Light mode | CSS variables + React state + localStorage |
| Typing animation | Custom `useState` + `useEffect` typewriter loop |
| Scroll reveal | `IntersectionObserver` via `useScrollReveal` hook |
| Skill bars | CSS `var(--target-width)` animated on `.visible` |
| Mobile nav | Hamburger menu with CSS transitions |
| Form validation | Client-side validation with inline error messages |
| Project cards | Hover lift + accent border + P/S breakdown |

---

Built by Atharva Shyam Samrat · samrat9473@gmail.com
