---
layout: default
title: Home
---

# Welcome to Tech Wiki

A comprehensive wiki for all tech stuff.

## Topics

- [Copilot CLI Setup Guide](copilot-cli/setup.md) - How to set up GitHub Copilot CLI on Windows & macOS

---

<style>
/* Theme toggle button */
.theme-toggle {
  position: fixed;
  top: 20px;
  right: 20px;
  background: none;
  border: 2px solid currentColor;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  cursor: pointer;
  font-size: 20px;
  z-index: 1000;
  transition: transform 0.3s ease;
}

.theme-toggle:hover {
  transform: scale(1.1);
}

/* Dark theme styles */
html[data-theme="dark"] {
  filter: invert(1) hue-rotate(180deg);
}

html[data-theme="dark"] img,
html[data-theme="dark"] video,
html[data-theme="dark"] .theme-toggle {
  filter: invert(1) hue-rotate(180deg);
}

/* Smooth transition */
html {
  transition: filter 0.3s ease;
}
</style>

<button class="theme-toggle" onclick="toggleTheme()" aria-label="Toggle dark mode">🌙</button>

<script>
function getPreferredTheme() {
  const stored = localStorage.getItem('theme');
  if (stored) return stored;
  return window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light';
}

function setTheme(theme) {
  document.documentElement.setAttribute('data-theme', theme);
  localStorage.setItem('theme', theme);
  updateToggleButton(theme);
}

function updateToggleButton(theme) {
  const button = document.querySelector('.theme-toggle');
  if (button) {
    button.textContent = theme === 'dark' ? '☀️' : '🌙';
  }
}

function toggleTheme() {
  const current = document.documentElement.getAttribute('data-theme') || 'light';
  const next = current === 'dark' ? 'light' : 'dark';
  setTheme(next);
}

// Initialize theme on page load
document.addEventListener('DOMContentLoaded', function() {
  setTheme(getPreferredTheme());
});

// Also run immediately for faster initialization
setTheme(getPreferredTheme());

// Listen for system theme changes
window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', function(e) {
  if (!localStorage.getItem('theme')) {
    setTheme(e.matches ? 'dark' : 'light');
  }
});
</script>
