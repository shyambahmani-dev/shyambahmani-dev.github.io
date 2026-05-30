# shyambahmani-dev.github.io

Personal site. Thoughts, long reads, and just chilling.

**→ [shyambahmani-dev.github.io](https://shyambahmani-dev.github.io)**

---

## What this is

A minimal personal website with three sections — **Thoughts** (short unfiltered posts), **Blog** (long reads), and **About**. Built with React + Vite. No CMS, no database, no backend. Content lives as plain Markdown files and gets baked into the site at build time.

---

## Project structure

```
src/
  content/
    posts/          ← blog post markdown files
    thoughts/       ← thought markdown files
  pages/            ← React pages (Thoughts, Blog, About)
  components/       ← Navbar, Footer, Topbar
  data/             ← loads and parses the markdown files (don't touch)
  index.css         ← all styles, one file
  App.jsx           ← root component

public/
  images/
    posts/          ← images used in blog posts
    thoughts/       ← images used in thoughts
  videos/
    posts/          ← videos used in blog posts
    thoughts/       ← videos used in thoughts

dist/               ← built output (this is what goes on GitHub Pages)
```

---

## Running locally

```bash
npm install
npm run dev
```

---

## How to publish content

1. Add or edit a `.md` file in `src/content/posts/` or `src/content/thoughts/`
2. Run `npm run build`
3. Drag the contents of `dist/` onto the GitHub repo in the browser
4. Done — GitHub Pages serves the updated site within a minute or two

You don't need to delete old files first. Just drop the new build on top and GitHub will overwrite what changed.

---

## Adding a thought

Create a new `.md` file in `src/content/thoughts/` (any filename works):

```markdown
---
date: May 31, 2026
---

Your thought here. *Italics* work. So does **bold**.
```

Thoughts are short — a sentence to a paragraph. They show up in reverse chronological order.

---

## Adding a blog post

Create a new `.md` file in `src/content/posts/` (the filename becomes the slug):

```markdown
---
title: Your Post Title
date: May 31, 2026
readTime: 4 min read
excerpt: One line that shows up in the post list as a teaser.
---

Full content here. Supports all standard Markdown.

## Subheadings work

So do lists, blockquotes, bold, italic, code blocks — all of it.

> Blockquotes look like this.

- List item one
- List item two
```

---

## Adding images

Put image files in:
- `public/images/posts/` — for blog post images
- `public/images/thoughts/` — for thought images

Then reference them in your markdown:

```markdown
![Description of image](/images/posts/my-photo.jpg)
```

Images are automatically included in the build and will show up on the site.

---

## Adding videos

Put video files in:
- `public/videos/posts/` — for blog post videos
- `public/videos/thoughts/` — for thought videos

Markdown doesn't have a native video tag, so use HTML directly inside your `.md` file:

```markdown
<video controls width="100%">
  <source src="/videos/posts/my-video.mp4" type="video/mp4" />
</video>
```

---

## Editing the About page

Open `src/pages/About.jsx` and edit the text and links directly. It's straightforward HTML-like JSX — just change the words and swap in real URLs for Instagram, GitHub, and email.

---

## Editing styles

All styles are in one file: `src/index.css`. The design uses CSS variables defined at the top:

```css
--bg: #0c0a0a        /* page background */
--ink: #ece4dd       /* main text */
--accent: #c44a5a    /* red/rose accent colour */
--line: #2a2222      /* borders */
```

Change those variables to retheme the whole site at once.

---

## Stack

- React + Vite
- Single CSS file, no UI library
- Markdown parsed by [marked.js](https://marked.js.org/) at runtime
- Fonts: Fraunces, Open Sans, JetBrains Mono via Google Fonts
- Hosted on GitHub Pages
