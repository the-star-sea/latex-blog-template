# LaTeX Blog Template

A minimal template for publishing a LaTeX-written blog post or note with GitHub Pages.

## What it does

- Write your content in `main.tex`
- GitHub Actions compiles it into `main.pdf`
- GitHub Pages publishes a small landing page that embeds the PDF
- The generated site is easy to fork and reuse

## Files

- `main.tex` — your post / note / article
- `index.html` — lightweight web wrapper for the PDF
- `.github/workflows/deploy.yml` — compile + deploy workflow
- `examples/` — a few small sample blog posts

## How to use

1. Edit `main.tex`
2. Push to `main`
3. Wait for the GitHub Action to finish
4. Open your GitHub Pages URL

## Local build

If you want to compile locally:

```bash
latexmk -xelatex -interaction=nonstopmode -halt-on-error main.tex
```

## Notes

- The workflow uses XeLaTeX for better Unicode / CJK compatibility
- The published page embeds `main.pdf` and also provides a direct PDF link
- You can rename `main.tex`, but then update the workflow accordingly

## Suggested use cases

- personal essays
- research notes
- course writeups
- technical blog posts
- bilingual posts written in LaTeX

## Included examples

- `examples/minimal-blog.tex` — a very small English post
- `examples/bilingual-blog.tex` — a simple Chinese/English mixed post

If you want to start from one of them, copy it over `main.tex` and push.
