# Assignment_3_WebPage

/* Base (light) theme */
:root {
  --bg: #ffffff;
  --fg: #111111;
  --link: #0645ad;
}

body {
  margin: 0;
  font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
  background: var(--bg);
  color: var(--fg);
  line-height: 1.6;
}

header {
  padding: 12px 16px;
}

h1 {
  margin: 0 0 8px 0;
  font-size: 2.4rem;
  font-weight: 800;
}

nav ul {
  margin: 8px 0;
  padding-left: 20px; /* bullets like the screenshot */
}

nav a {
  color: var(--link);
  text-decoration: underline;
}

.name-form {
  margin: 12px 0;
  display: flex;
  gap: 8px;
}

.name-form input {
  padding: 6px 8px;
}

button {
  padding: 6px 10px;
  border: 1px solid #bbb;
  border-radius: 4px;
  background: #f3f3f3;
  cursor: pointer;
}

main {
  padding: 0 16px 32px 16px;
}

h2 {
  font-size: 1.8rem;
  margin-top: 24px;
}

h3 {
  font-size: 1.2rem;
  margin-top: 20px;
}

/* Dark theme */
.dark-theme {
  --bg: #0f0f12;
  --fg: #eeeeee;
  --link: #8ab4f8;
}

.dark-theme button {
  background: #1f1f23;
  border-color: #333;
}

// Theme toggle + greeting via query string
document.addEventListener('DOMContentLoaded', () => {
  // Theme toggle
  const btn = document.getElementById('theme-toggle');
  btn?.addEventListener('click', () => {
    document.body.classList.toggle('dark-theme');
    const mode = document.body.classList.contains('dark-theme') ? 'dark' : 'light';
    localStorage.setItem('theme', mode);
  });

  // Load saved theme
  const savedTheme = localStorage.getItem('theme');
  if (savedTheme === 'dark') document.body.classList.add('dark-theme');

  // Greeting in the header title
  const params = new URLSearchParams(window.location.search);
  const name = params.get('user_name');
  const title = document.getElementById('page-title');
  if (name && title) {
    title.textContent = `Hello, ${name}`;
    localStorage.setItem('last_name', name);
  } else {
    const stored = localStorage.getItem('last_name');
    if (stored && title) title.textContent = `Hello, ${stored}`;
  }

  
 Project Title

My First-Year University Web Page

Project Description

This project is a simple multi-page website built using HTML, CSS, and JavaScript.
It represents my first-year experience at university, the courses I am learning, and includes a To-Do List application.
The web page demonstrates interactive elements such as theme toggling, image switching, dynamic headings, date/time display, and local storage features.

⚙️ How to Install and Run the Project

Clone or download this repository:

git clone https://github.com/your-username/Assignment_3_WebPage.git


Open the folder Assignment_3_WebPage.

Open the file index.html in any modern web browser (Google Chrome, Firefox, Edge).

Make sure JavaScript is enabled in your browser.

 How to Use the Project

Home Page: Shows an introduction and welcome message.

Courses Page: Lists my first-year courses.

Theme Toggle: Use the "Toggle Theme" button to switch between light and dark mode.

Image Buttons: Click buttons to change the displayed image and photographer name.

User Greeting: Enter your name, and the page will greet you with "Hello, <name>".

To-Do List: Accessible via password; allows you to add, remove, save, and load learning tasks.

Local Storage: Saves user preferences (theme and name) and restores them on reload.

 Credits

Project created by [Your Name] for Assignment 3.
