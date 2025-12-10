# Study-website

A lightweight static study/quiz website built with HTML, JavaScript and Tailwind CSS. The project provides a front-end quiz interface (questions and UI logic) that runs entirely in the browser. It is easy to customize by editing the Questions.js file and the styles in the CSS source.

Key technologies
- HTML, JavaScript, CSS
- Tailwind CSS for utility-first styling
- Node/npm used for building the CSS (tailwind CLI and dependencies are included in the repository)

Quick summary
- Public-facing app files are under `public/` (core HTML, JS, and generated CSS).
- Tailwind source styles live under `src/input.css`. The compiled Tailwind output is `public/output.css`.
- Quiz data and logic are in `public/Questions.js` and `public/index.js`.
- `tailwind.config.js` contains the Tailwind configuration (custom fonts and content paths).

Features
- Browser-run quiz with question data separated into a single file for easy editing.
- Tailwind-based responsive styling with a custom font stack defined in the Tailwind config.
- Minimal tooling: only a Tailwind build step is required to regenerate CSS from the `src` input file.

Repository structure (important files)
- public/
  - index.html — Main page for the study/quiz site.
  - index.js — Main application logic and UI glue.
  - Questions.js — Quiz questions/data (edit this to change the quiz content).
  - output.css — Compiled CSS used by the site (generated).
- src/
  - input.css — Tailwind source file(s) and custom CSS (used to generate `public/output.css`).
- tailwind.config.js — Tailwind CSS configuration (content paths, font families).
- package.json & package-lock.json — Node dependencies and metadata.

Getting started (development)
1. Clone the repository:
   git clone https://github.com/abdulhaseeb8ah/Study-website.git
   cd Study-website

2. Install dependencies:
   npm install

3. Build the Tailwind CSS
   - If you want to generate `public/output.css` from `src/input.css` manually using the Tailwind CLI, run:
     npx tailwindcss -i ./src/input.css -o ./public/output.css --minify
   - To watch for changes during development:
     npx tailwindcss -i ./src/input.css -o ./public/output.css --watch

   Note: If there is a build script present in package.json (for example `npm run build` or `npm run dev`), you can use that instead:
     npm run build
     or
     npm run dev

4. Open the site in your browser:
   Open `public/index.html` (for example: double-click or serve the `public` directory with a simple local server).

Customizing the quiz
- Edit `public/Questions.js` to add, remove, or change quiz questions and answers. The main `index.js` reads this file to populate the UI.
- Update layout and behavior by changing `public/index.html` and `public/index.js`.
- Change styles by editing `src/input.css` and rebuilding `public/output.css`.

Fonts and styling
- The Tailwind config defines several font-family keys (for example: `black-ops-one`, `montserrat`, `roboto`, etc.). To use external fonts (Google Fonts), ensure they are loaded in `public/index.html` or add `<link>` tags to include them.

Deployment
- The app is purely static, so you can deploy the `public/` folder to any static hosting provider (GitHub Pages, Netlify, Vercel, Firebase Hosting, etc.).
- Before deploying, ensure `public/output.css` is present and up-to-date (build step from `src/input.css`).

Notes and recommendations
- Keep `Questions.js` human-readable and optionally versioned separately if you plan to maintain many different quizzes.
- Consider adding a small build script to package.json (if not already present) to automate the Tailwind build command for contributors.
- Add a LICENSE and CONTRIBUTING.md if you want to define reuse and contribution guidelines.

Troubleshooting
- If styles look incorrect, confirm that `public/output.css` exists and is the latest build from `src/input.css`.
- If new fonts are not applied, make sure they are referenced in `public/index.html` (via Google Fonts or local files) and that the corresponding font keys in `tailwind.config.js` are being used in the markup.

Contributing
- Contributions are welcome (bug fixes, improved UI, more question sets). Open an issue or a pull request with proposed changes and a short description of what you changed and why.

License
- No license file detected in the repository. If you'd like this project to be open-source, add a LICENSE file (for example, MIT) and update package.json accordingly.

Contact / Maintainer
- Repository owner: abdulhaseeb8ah
- For questions about the project, open an issue in the repository.

Enjoy customizing and using the Study-website!
