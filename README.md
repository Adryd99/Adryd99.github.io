# adryd99.github.io

Personal site of Adrian Dumitru, built with [Eleventy](https://www.11ty.dev/) and published on GitHub Pages.

## Write a new note

1. Create a file in `src/notes/` named `YYYY-MM-DD-short-title.md`.
2. Start it with:

   ```
   ---
   title: The title of the note
   summary: One or two sentences shown on the home page.
   ---
   ```

3. Write the text in Markdown below. Put images in `src/assets/img/notes/` and use them like this:

   ```
   <figure>
     <img src="/assets/img/notes/my-image.jpg" alt="What the image shows">
     <figcaption>Caption under the image.</figcaption>
   </figure>
   ```

4. Commit and push to `main`. The site rebuilds and goes live in about a minute.

## Edit a case study

Case studies live in `src/work/`. The `order` field decides their position on the home page.

## Run it locally

```
npm install
npm start
```

Then open http://localhost:8080.

## Fonts

Archivo and Source Serif 4 are self-hosted under the SIL Open Font License (see `src/assets/fonts/`).
