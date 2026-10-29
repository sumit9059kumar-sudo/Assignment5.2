File 1: index.html
HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assignment 5.2 - CSS Selectors Practice</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <!-- Element Selector Target -->
  <header>
    <h1>CSS Selectors Practice</h1>
    <p>Demonstrating various CSS selectors, cascade, and specificity rules.</p>
  </header>

  <main>
    <!-- Grouping Selector Target (h2, h3) -->
    <h2>Card Showcase</h2>

    <!-- Class Selector Target (.card) -->
    <div class="card">
      <h3>Card Title 1</h3>
      <p>This is the first card element styled using a class selector.</p>
    </div>

    <div class="card">
      <h3>Card Title 2</h3>
      <p>This is the second card sharing the same class styling.</p>
    </div>

    <!-- ID Selector Target (#featured-section) -->
    <!-- Conflicting Rule Test: Has class "card" AND id "featured-section" -->
    <section id="featured-section" class="card">
      <h3>Featured Section</h3>
      <p>This element tests specificity: ID selector vs. Class selector.</p>
    </section>
  </main>

  <footer>
    <p>&copy; 2026 Web Development Assignment</p>
  </footer>

</body>
</html>
File 2: styles.css
CSS
/* 1. Universal Selector (*) */
/* Applies a basic reset for margins, padding, and box-sizing across all elements */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Base Body Styles */
body {
  font-family: Arial, sans-serif;
  line-height: 1.6;
  background-color: #f4f4f9;
  color: #333;
  padding: 20px;
}

/* 2. Element Selector */
/* Target all paragraph (<p>) tags on the page */
p {
  color: #555;
  font-size: 1rem;
}

/* 3. Grouping Selector */
/* Apply shared heading styles to both <h2> and <h3> elements */
h2, h3 {
  font-family: 'Georgia', serif;
  margin-bottom: 10px;
  color: #2c3e50;
}

/* 4. Class Selector (.card) */
/* Style multiple section/div components with a reusable card layout */
.card {
  background-color: #ffffff;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 20px;
  margin-bottom: 15px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* 5. ID Selector (#featured-section) */
/* Style a single specific element uniquely using its ID */
#featured-section {
  background-color: #e8f4f8;
  border-left: 5px solid #2980b9;
}

/* 6. Conflict & Specificity Demonstration */
/* Rule A: Class selector targeting paragraph inside .card */
.card p {
  color: #27ae60; /* Green text */
}

/* Rule B: Higher specificity rule overriding Rule A */
#featured-section p {
  color: #c0392b; /* Red text */
}
Explanation of Selectors Used
Universal Selector (*): Applied to all HTML elements to perform a standard CSS reset (margin: 0; padding: 0; box-sizing: border-box;).

Element Selector (p): Targets all <p> HTML tags directly to establish baseline font colors and sizes across the body text.

Class Selector (.card): Targets elements with class="card", allowing multiple sections and divs to share a structured card component design (borders, padding, shadow).

ID Selector (#featured-section): Uniquely targets the element with id="featured-section" to give it a custom highlight background color and accent border.

Grouping Selector (h2, h3): Groups <h2> and <h3> tags separated by commas to apply identical font families and bottom margins in a single CSS block without duplicating code.

Cascade & Specificity Demonstration:

A conflicting situation was created for the paragraph inside #featured-section.

.card p sets the text color to green (Specificity: 0, 0, 1, 1).

#featured-section p sets the text color to red (Specificity: 0, 1, 0, 1).

Observation: Because the ID selector (#featured-section p) has higher specificity than the class selector (.card p), the cascade resolves in favor of #featured-section p, making the paragraph text inside the featured section red.