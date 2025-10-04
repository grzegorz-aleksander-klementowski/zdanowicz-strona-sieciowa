![CI](https://github.com/grzegorz-aleksander-klementowski/zdanowicz-strona-sieciowa/actions/workflows/ci.yml/badge.svg)

# Zdanowicz Podnośniki

Static marketing site for podnośniki koszowe (boom lift) services around Wojcieszów and Jelenia Góra. The layout is based on the Start Bootstrap **Agency** template, while all copy, imagery, and color adjustments were created for Piotr Zdanowicz F.U.H.

## What’s inside
- Responsive single-page layout covering services, realizations, company timeline, and certifications.
- Optimized assets under `assets/` with custom photography and iconography.
- Accessibility and SEO tweaks (Polish language metadata, localized copy, structured sections).
- Lightweight GitHub Actions CI (`.github/workflows/ci.yml`) ready for Stylelint, ESLint, and Prettier checks once configs are added.
- Dedicated W3C validation workflow (`.github/workflows/w3c-validation.yml`) running the official Nu validator against HTML and CSS.

## Template attribution
- **UI framework:** [Start Bootstrap – Agency v7.0.12](https://startbootstrap.com/theme/agency) by Start Bootstrap LLC (MIT License).
- **Modifications:** Grzegorz Aleksander Klementowski — bespoke text, photography, palette, and business details.
- Please retain both this notice and the upstream license metadata when redistributing.

## Getting started
1. Clone the repository and move into the project directory.
2. Open `index.html` directly in a browser, or run a simple server (`python3 -m http.server`) if you need same-origin behavior.
3. Optional: run the checks from CI locally
   - `npx --yes html-validator-cli --file index.html --format text`
   - `npx --yes stylelint "css/**/*.css"` (requires a `.stylelintrc*` file)
   - `npx --yes eslint "js/**/*.js"` (requires a `.eslintrc*` file)
   - `npx --yes prettier --check .` (requires a `.prettierrc*` file)
   - `docker run --rm -v "$(pwd)":/site ghcr.io/validator/validator:latest /vnu-runtime-image/bin/vnu --errors-only --no-verbose /site/index.html /site/jelenia-gora.html /site/css/styles.css`

## Project structure
- `index.html` – main landing page markup.
- `css/styles.css` – Start Bootstrap stylesheet with local overrides.
- `js/scripts.js` – minimal nav interactions from the Agency theme.
- `assets/` – brand imagery, icons, and photos tailored to the business.
- `.github/workflows/ci.yml` – GitHub Actions pipeline configuration.

## License
- Website content (text, photos, and customizations) © Piotr Zdanowicz Firma Usługowo Handlowa / Grzegorz Aleksander Klementowski, released under the MIT License (see `LICENSE`).
- Agency template assets © Start Bootstrap LLC, distributed under the MIT License. Review the upstream license if you reuse or extend the template.
