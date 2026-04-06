# LaTeX Blog Template

A minimal template for publishing a LaTeX-written blog post with a homepage style closer to the-star-sea/blog than to a poem or PDF-reader layout.

## What it does

- Write your content in `main.tex`
- GitHub Actions compiles it into `main.pdf`
- GitHub Pages publishes a blog-style landing page that links to the generated PDF
- The generated site is easy to fork and reuse

## Files

- `main.tex` — your post / note / article
- `index.html` — blog-style landing page
- `style.css` — homepage styling inspired by the existing blog aesthetic
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
- The published page is intentionally simple and blog-like, not a poem-style reader shell
- By default it links to `main.pdf`
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
