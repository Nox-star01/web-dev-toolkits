# ⚡ Web Dev Toolkit

A lightweight collection of reusable components, utilities, animations, and JavaScript helpers for modern web development.

Built to provide simple, dependency-free building blocks that can be dropped into almost any website.

## ✨ Features

- Responsive UI components
- Modern CSS animations
- JavaScript utilities
- Smooth scrolling
- Copy-to-clipboard utility
- Dark mode support
- Loading animations
- Glassmorphism components
- Responsive navigation
- No frameworks required

## 📁 Structure

web-dev-toolkit/
├── css/
│   ├── animations.css
│   └── components.css
├── js/
│   └── utilities.js
├── examples/
│   └── index.html
├── LICENSE
└── README.md

## 🚀 Usage

Download or clone the repository.

```bash
git clone https://github.com/YOUR-USERNAME/web-dev-toolkit.git


<link rel="stylesheet" href="css/components.css">
<link rel="stylesheet" href="css/animations.css">

<script src="js/utilities.js"></script>

copyText("Hello World");

smoothScroll("#about");

toggleDarkMode();

🎨 UI Components
The toolkit includes reusable:
Buttons
Cards
Glass panels
Navigation bars
Badges
Loading indicators
🤝 Contributing
Contributions, improvements, and suggestions are welcome.
Fork the repository, make your changes, and submit a pull request.
📄 License
Released under the MIT License.


Then create **`js/utilities.js`**:

```javascript
// Web Dev Toolkit
// Lightweight JavaScript utilities

function copyText(text) {
    if (!navigator.clipboard) {
        console.error("Clipboard API is not supported.");
        return;
    }

    navigator.clipboard.writeText(text)
        .then(() => console.log("Copied to clipboard"))
        .catch(error => console.error("Copy failed:", error));
}

function smoothScroll(selector) {
    const element = document.querySelector(selector);

    if (element) {
        element.scrollIntoView({
            behavior: "smooth",
            block: "start"
        });
    }
}

function toggleDarkMode() {
    document.documentElement.classList.toggle("dark-mode");
}

function debounce(callback, delay = 300) {
    let timer;

    return (...args) => {
        clearTimeout(timer);

        timer = setTimeout(() => {
            callback(...args);
        }, delay);
    };
}

function generateID(length = 8) {
    const chars =
        "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";

    let result = "";

    for (let i = 0; i < length; i++) {
        result += chars.charAt(
            Math.floor(Math.random() * chars.length)
        );
    }

    return result;
}

function formatNumber(number) {
    return new Intl.NumberFormat().format(number);
}

function sleep(ms) {
    return new Promise(resolve => setTimeout(resolve, ms));
}


Create css/animations.css:

/* Web Dev Toolkit Animations */

.fade-in {
    animation: fadeIn 0.6s ease forwards;
}

.slide-up {
    animation: slideUp 0.6s ease forwards;
}

.scale-in {
    animation: scaleIn 0.4s ease forwards;
}

.float {
    animation: float 3s ease-in-out infinite;
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}

@keyframes slideUp {
    from {
        opacity: 0;
        transform: translateY(30px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes scaleIn {
    from {
        opacity: 0;
        transform: scale(0.9);
    }

    to {
        opacity: 1;
        transform: scale(1);
    }
}

@keyframes float {
    0%,
    100% {
        transform: translateY(0);
    }

    50% {
        transform: translateY(-10px);
    }
}

And css/components.css:

/* Web Dev Toolkit Components */

:root {
    --background: #ffffff;
    --surface: #f5f5f5;
    --text: #111111;
    --border: #dddddd;
}

.dark-mode {
    --background: #090909;
    --surface: #151515;
    --text: #ffffff;
    --border: #292929;
}

body {
    margin: 0;
    background: var(--background);
    color: var(--text);
    font-family: Inter, Arial, sans-serif;
    transition: background 0.3s ease, color 0.3s ease;
}

.btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 12px 20px;
    border: 0;
    border-radius: 10px;
    cursor: pointer;
    font-weight: 600;
    transition: transform 0.2s ease;
}

.btn:hover {
    transform: translateY(-2px);
}

.card {
    padding: 24px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
}

.glass {
    background: rgba(255, 255, 255, 0.08);
    backdrop-filter: blur(18px);
    -webkit-backdrop-filter: blur(18px);
    border: 1px solid rgba(255, 255, 255, 0.12);
    border-radius: 16px;
}

.badge {
    display: inline-block;
    padding: 5px 10px;
    border: 1px solid var(--border);
    border-radius: 999px;
    font-size: 12px;
}

.container {
    width: min(1100px, 90%);
    margin: 0 auto;
}