# LeetCode Pattern Practice Tool

Welcome to the LeetCode Pattern Practice Tool! This is a web-based, interactive single-page application designed to help users learn and practice common algorithmic patterns encountered in LeetCode-style problems. The tool provides explanations, sample problems, and detailed step-by-step walkthroughs for various patterns, along with a random LeetCode problem generator.

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [How to Use This Tool](#how-to-use-this-tool)
- [Technologies Used](#technologies-used)
- [Core Patterns Covered](#core-patterns-covered)
- [Content Structure for Each Pattern](#content-structure-for-each-pattern)
- [Random Question Generator](#random-question-generator)
- [Future Enhancements (Ideas)](#future-enhancements-ideas)

## Project Overview

This tool aims to be a one-stop-shop for understanding and internalizing key algorithmic patterns crucial for coding interviews and competitive programming. It features a dark mode interface with a yellow accent color for a pleasant user experience. Users can select a specific pattern from the sidebar to view its detailed explanation, a relevant sample problem, and a comprehensive walkthrough of the solution. Additionally, a random LeetCode problem suggestion feature is included to encourage varied practice.

## Features

* **Interactive Sidebar Navigation:** Easily switch between different algorithmic patterns and the random question generator.
* **Detailed Pattern Explanations:** Each pattern section provides a clear description of the pattern, its use cases, and when to apply it.
* **Sample Problems:** Illustrative LeetCode-style problems are presented for each pattern.
* **Collapsible Walkthroughs:** Step-by-step solutions for sample problems, including Python code examples and complexity analysis. These steps can be expanded or collapsed for focused learning.
* **Syntax Highlighting:** Python code examples are clearly formatted and highlighted using Highlight.js for better readability.
* **Random LeetCode Problem Generator:** Suggests a random problem from a curated list, complete with its common pattern(s) and a direct link to the problem on LeetCode.
* **Responsive Design:** The interface adapts to different screen sizes, with a collapsible sidebar for desktop and an overlay sidebar for mobile.
* **Dark Mode UI:** Aesthetically pleasing dark theme with yellow accents.
* **Minimizable Sidebar:** The sidebar can be minimized on desktop to maximize content viewing area.
* **Mobile-Friendly Sidebar:** On smaller screens, the sidebar acts as an overlay, toggleable via a dedicated button.

## Project Structure

The project is a single HTML file (`index.html`) that includes embedded CSS and JavaScript to create a dynamic user experience:

* **`index.html` (Main File):**
    * **HTML Structure:** Defines the layout including the sidebar (`<aside id="sidebar">`) and the main content area (`<main id="main-content">`). Each pattern and the random question generator have their own content `div`s (e.g., `<div id="sliding-window" class="pattern-content">`).
    * **CSS (Embedded in `<style>` tags and Tailwind CSS):**
        * **Tailwind CSS:** Utilized via CDN for rapid UI development with utility classes.
        * **Custom CSS:** Includes styles for the "Inter" font, initial content hiding, code block styling (dark mode), sidebar button styling (including active states with yellow accent), collapsible walkthrough steps, random question display, and sidebar minimization/mobile overlay behavior.
    * **JavaScript (Embedded in `<script>` tags):**
        * Manages all interactivity.
        * **DOM Element Selection:** References to sidebar, main content, buttons, content sections, etc.
        * **LeetCode Problem Bank:** An array `leetcodeProblems` stores objects, each representing a problem with its name, associated pattern(s), and a LeetCode link.
        * **Sidebar Toggle Functionality:** `toggleSidebar()` for desktop minimization and mobile overlay.
        * **Content Switching:** `showContent(contentId)` function to display the relevant pattern or random question generator section and update active button states.
        * **Collapsible Walkthroughs:** `toggleWalkthroughStep()` allows users to expand/collapse detailed solution steps.
        * **Random Question Generation:** `displayRandomQuestion()` selects and shows a random problem from the `leetcodeProblems` array.
        * **Event Listeners:** Attached to sidebar buttons, walkthrough headers, and the random question generator button.
        * **Initialization (`DOMContentLoaded`):** Sets up initial states (e.g., hiding content, applying syntax highlighting with `hljs.highlightAll()`, setting initial sidebar state based on screen size).
        * **Resize Handling:** Adjusts sidebar icon and behavior on window resize.

## How to Use This Tool

1.  **Open `index.html`:** Save the HTML file to your computer and open it in a modern web browser (e.g., Chrome, Firefox, Edge).
2.  **Navigate Patterns:**
    * Use the sidebar on the left to select an algorithmic pattern (e.g., "Sliding Window," "Dynamic Programming").
    * Clicking a pattern button will display its dedicated content in the main area.
    * On mobile, the sidebar toggle button (hamburger/chevron icon) will open/close the sidebar.
3.  **Study Content:**
    * Read the **Explanation** of the selected pattern.
    * Review the **Sample Problem**.
    * Expand the **Walkthrough** steps one by one to understand the solution process, including code examples and complexity.
4.  **Practice with Random Questions:**
    * Click the "Random Question" button in the "Practice" section of the sidebar.
    * A random LeetCode problem will be displayed with its name, common pattern(s), and a link to the problem on LeetCode.
    * Click "Generate Random Problem" again for a new suggestion.
5.  **Minimize Sidebar (Desktop):**
    * Click the chevron icon on the right edge of the sidebar to minimize/expand it for more content space.

## Technologies Used

* **HTML5:** For the overall structure of the application.
* **CSS3:** For custom styling, animations, and layout enhancements.
    * **Tailwind CSS:** A utility-first CSS framework (loaded via CDN) for rapid and responsive UI development.
* **JavaScript (Vanilla):** For all client-side logic, interactivity, and DOM manipulation.
* **Font Awesome:** For icons (e.g., chevrons, external link icon), loaded via CDN.
* **Google Fonts:** For the "Inter" sans-serif font.
* **Highlight.js:** For syntax highlighting of Python code examples within `<pre><code>` blocks (loaded via CDN).

## Core Patterns Covered

The sidebar lists several core algorithmic patterns for study, including:

* Sliding Window
* Dynamic Programming (DP)
* Two Pointers
* Fast & Slow Pointers
* Breadth-First Search (BFS)
* Depth-First Search (DFS)
* Merge Intervals
* Heap / Priority Queue

## Content Structure for Each Pattern

Each pattern section in the main content area generally follows this structure:

1.  **Title:** The name of the pattern.
2.  **Explanation:**
    * A detailed description of what the pattern is.
    * How it generally works.
    * Common scenarios or types of problems where this pattern is applicable ("When to use it").
3.  **Sample Problem:**
    * A clear problem statement, often similar to a LeetCode problem.
    * Example inputs and outputs.
4.  **Walkthrough:**
    * A series of collapsible steps detailing the thought process and implementation of a solution.
    * Each step can be expanded to reveal more information.
    * Python code snippets demonstrating the implementation.
    * Explanation of specific parts of the code or logic.
    * Complexity analysis (Time and Space).

## Random Question Generator

* Accessible via the "Random Question" button in the sidebar.
* When clicked, the "Generate Random Problem" button fetches a random problem from a predefined JavaScript array (`leetcodeProblems`).
* The display area shows:
    * The problem name.
    * The common algorithmic pattern(s) associated with it.
    * A direct link to the problem on the LeetCode website.

## Future Enhancements (Ideas)

* **More Patterns:** Add more advanced or specialized algorithmic patterns.
* **Expanded Problem Bank:** Increase the number and variety of problems in the random generator.
* **Filter Random Questions by Pattern:** Allow users to get random questions specific to a chosen pattern.
* **User Notes:** Allow users to add personal notes to each pattern.
* **Progress Tracking:** Mark patterns or problems as "learned" or "to practice."
* **Interactive Code Editor:** Embed a simple code editor for users to try out solutions directly in the browser.
* **Difficulty Levels:** Tag problems with difficulty levels (Easy, Medium, Hard).
* **Search Functionality:** Search for patterns or keywords within the explanations.
* **User Accounts & Persistence:** Store user progress and notes if expanded into a larger application.
