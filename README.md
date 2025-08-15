# Admin-dashboard-with-CSS-grid-layout
A clean and responsive Admin Dashboard built using HTML, CSS, and CSS Grid. It’s designed for managing data, monitoring stats, and controlling settings — all in one place.
# html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Admin Dashboard</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <!-- Invisible checkbox to toggle theme -->
  <input type="checkbox" id="theme-toggle" />

  <div class="container">
    <header>
      <div><strong>Admin Dashboard</strong></div>
      <div class="theme-switch">
        <label for="theme-toggle" class="theme-label">☑ Dark Mode</label>
      </div>
    </header>

    <aside>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Users</a></li>
        <li><a href="#">Settings</a></li>
      </ul>
    </aside>

    <main>
      <h3>Welcome, Admin!</h3>
      <p>This is the main content area. Add charts, tables, or reports here.</p>
    </main>

    <footer>
      © 2025 Admin Panel
    </footer>
  </div>
</body>
</html>

#CSS
:root {
  --bg-color: #ffffff;
  --text-color: #000000;
  --sidebar-bg: #f0f0f0;
  --header-footer-bg: #4CAF50;
  --link-color: #6a0dad;
}

/* Dark mode when checkbox is checked */
#theme-toggle:checked ~ .container {
  --bg-color: #1e1e1e;
  --text-color: #f0f0f0;
  --sidebar-bg: #2c2c2c;
  --header-footer-bg: #333333;
  --link-color: #9c88ff;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background-color: var(--bg-color);
  color: var(--text-color);
}

.container {
  display: grid;
  grid-template-rows: auto 1fr auto;
  grid-template-columns: 200px 1fr;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  height: 100vh;
}

header {
  grid-area: header;
  background-color: var(--header-footer-bg);
  color: white;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

aside {
  grid-area: sidebar;
  background-color: var(--sidebar-bg);
  padding: 1rem;
}

main {
  grid-area: main;
  padding: 1rem;
}

footer {
  grid-area: footer;
  background-color: var(--header-footer-bg);
  color: white;
  text-align: center;
  padding: 0.5rem;
}

a {
  color: var(--link-color);
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

.theme-switch {
  font-size: 0.9rem;
  color: white;
}

#theme-toggle {
  display: none;
}

.theme-label {
  cursor: pointer;
  user-select: none;
}

