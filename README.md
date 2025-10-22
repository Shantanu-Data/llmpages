# LLMPages

## Summary
LLMPages is a static GitHub Pages site designed to showcase a collection of diverse content, including creative writing pieces, ethical dilemmas, technical assets like an SVG illustration, JSON-formatted data (restaurant recommendations, economic predictions), and standard project files (license, unique identifier). It serves as a simple, interactive portfolio where users can view and download various generated or curated files.

## Live Demo
[Live Demo](https://shantanu-data.github.io/llmpages/)

## Setup
No setup is required to run this project. As a static HTML, CSS, and JavaScript website, it can be hosted directly on any web server or viewed by opening the `index.html` file in a web browser. The project leverages GitHub Pages for direct deployment.

## How to Use
Navigate to the [Live Demo](https://shantanu-data.github.io/llmpages/) link. The homepage (`index.html`) displays a grid of cards, each representing a different project file.
*   **View Content:** For files like JSON and SVG, click the "View Content" or "Toggle View" button to display their content directly on the page.
*   **Download Files:** Click the "Download [filename]" button on any card to download the respective file to your local machine.
*   **Navigation:** Use the top navigation bar to quickly jump to specific sections (project cards) on the page.
*   **UID Display:** The `uid.txt` card fetches and displays the unique identifier directly on the page, also providing a download link for the raw file.

## Code Explanation

This project is implemented as a single-page application using standard web technologies: HTML for structure, CSS for styling, and JavaScript for interactivity.

*   **`index.html` (HTML Structure):**
    *   This is the main entry point of the application.
    *   It uses **Bootstrap 5 CDN** for a responsive and modern user interface, including navigation, a hero section, and a grid of cards.
    *   Each project item (e.g., `ashravan.txt`, `dilemma.json`, `pelican.svg`) is represented by a Bootstrap card.
    *   Cards include a title, a brief description, and buttons for interaction.
    *   Dedicated `div` elements with `id`s are used to inject dynamic content or display static JSON/SVG code.
    *   Includes a `<nav>` bar for easy navigation between sections and a `<footer>` for copyright information.

*   **CSS (Styling):**
    *   **Bootstrap 5 CDN:** Provides a robust foundation for responsive design, component styling (cards, buttons, navbar), and grid layout.
    *   **Inline `<style>` Block:** Custom CSS rules are embedded directly in the `<head>` section to override or extend Bootstrap's default styles. This includes:
        *   General `body` typography and background.
        *   Styling for the `navbar` and `hero-section` (e.g., gradient background, larger fonts).
        *   Customizations for `card` elements (shadows, hover effects).
        *   Specific styles for `json-viewer` `pre` tags and `svg-container` to ensure proper display.
        *   A `btn-custom` class for distinctive button styling.

*   **JavaScript (Interactivity):**
    *   **Bootstrap 5 JS CDN:** Included at the end of the `<body>` to enable Bootstrap's interactive components, such as the responsive navbar and the `collapse` functionality used for toggling content visibility (e.g., JSON viewers, SVG display).
    *   **Embedded Content Storage:** The contents of files like `ashravan.txt`, `dilemma.json`, `about.md`, `pelican.svg`, `restaurant.json`, `prediction.json`, and `LICENSE` are stored as JavaScript string literals. This allows the files to be "downloaded" and "viewed" dynamically without needing separate requests for each file.
    *   **Download Functionality:** Event listeners are attached to all "Download" buttons. Upon clicking, the JavaScript:
        1.  Retrieves the associated content string, filename, and content type from `data-` attributes.
        2.  Creates a `Blob` object from the content.
        3.  Generates a temporary URL for the Blob.
        4.  Creates a virtual `<a>` element, sets its `href` and `download` attributes, programmatically "clicks" it to initiate the download, and then removes it, revoking the URL.
    *   **Content Display:**
        *   JSON content is pretty-printed and injected into `<code>` tags within `<pre>` elements.
        *   The `pelican.svg` content string is injected directly into an `svg-container` `div`, causing the SVG graphic to render on the page.
    *   **`uid.txt` Fetch:** On `DOMContentLoaded`, JavaScript uses the `fetch` API to asynchronously retrieve the content of `public/uid.txt`. This content is then displayed on the respective card.

## License
This project is licensed under the MIT License. See the `LICENSE` file for full details.