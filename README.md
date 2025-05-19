# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨











<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Interactive Page</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>

  <h1>Welcome Back!</h1>
  <button id="animateBtn">Click Me</button>
  <button onclick="setTheme('light')">Light Theme</button>
  <button onclick="setTheme('dark')">Dark Theme</button>

  <script src="script.js"></script>
</body>
</html>


---

🎨 style.css
css
body {
  font-family: Arial, sans-serif;
  text-align: center;
  transition: background-color 0.5s, color 0.5s;
}

button {
  padding: 10px 20px;
  margin: 10px;
  font-size: 16px;
  cursor: pointer;
  transition: transform 0.3s ease;
}

button.clicked {
  animation: bounce 0.6s;
}

@keyframes bounce {
  0%   { transform: scale(1); }
  50%  { transform: scale(1.2); }
  100% { transform: scale(1); }
}

body.light {
  background-color: #fff;
  color: #000;
}

body.dark {
  background-color: #222;
  color: #fff;
}


---

// Apply saved theme on load
document.addEventListener("DOMContentLoaded", () => {
  const savedTheme = localStorage.getItem("theme") || "light";
  document.body.classList.add(savedTheme);
});

// Set theme and store in localStorage
function setTheme(theme) {
  document.body.classList.remove("light", "dark");
  document.body.classList.add(theme);
  localStorage.setItem("theme", theme);
}

// Animate button on click
document.getElementById("animateBtn").addEventListener("click", function () {
  this.classList.add("clicked");
  setTimeout(() => this.classList.remove("clicked"), 600);
});
