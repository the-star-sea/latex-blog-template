# LaTeX Blog Template

A blog-style LaTeX template that uses GitHub Actions to compile posts and publish them with GitHub Pages.

This template is meant to feel closer to `the-star-sea/blog` than to a poem reader or a single PDF viewer page.

## What it does

- write posts in `posts/*.tex`
- GitHub Actions compiles every post into PDF
- `build_blog.py` generates:
  - a blog-style `index.html`
  - per-post HTML viewer pages in `dist/posts/`
  - `feed.xml`
- GitHub Pages deploys the generated site automatically

## Repository structure

- `posts/` — your LaTeX blog posts
- `blog.yaml` — titles / dates / publish flags
- `build_blog.py` — generates the blog homepage, viewers, and feed
- `requirements.txt` — Python dependency pin for the local builder and CI
- `style.css` — homepage style
- `.github/workflows/deploy.yml` — compile + deploy workflow
- `examples/` — extra small examples you can copy from

## How to use

1. Add or edit a post in `posts/`
2. Make sure it has a `\title{...}`
3. Update `blog.yaml` if you want to adjust ordering / visibility
4. Push to `main`
5. GitHub Actions will compile and deploy automatically

## Local test

Compile a post manually:

```bash
latexmk -xelatex -interaction=nonstopmode -halt-on-error posts/blog0.tex
```

Regenerate the blog index locally:

```bash
python -m pip install -r requirements.txt
python build_blog.py from_tex posts/blog0.tex posts/blog1.tex
cp style.css dist/style.css
```

Then open `dist/index.html`.

## Notes

- The workflow uses XeLaTeX for better Unicode / CJK compatibility
- The generated homepage is intentionally simple and blog-like
- Posts are rendered as PDFs and linked through lightweight HTML viewer pages
- You can remove the sample posts and replace them with your own

## Included starter content

- `posts/blog0.tex` — a simple English post
- `posts/blog1.tex` — a simple bilingual post
- `examples/` — extra lightweight examples
