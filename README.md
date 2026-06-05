# Resume, versioned with LinkRight

This repository hosts a versioned, publicly accessible resume published via [LinkRight](https://github.com/satvik-jain-iitd/linkright-skills).

The default format is LaTeX, compiled to PDF automatically by GitHub Actions. HTML is optional.

## How it works

Every time `/linkright-push` runs, it:

1. Writes the tailored resume as a `.tex` file (LaTeX, the default), or as HTML if you chose that path.
2. For LaTeX, also writes a tiny `index.html` that redirects to the compiled `resume.pdf`.
3. Commits with a tag, `<company>-<role>-<date>`, and pushes to this repo.
4. On push, the GitHub Action compiles every `.tex` to PDF with XeLaTeX and commits the PDF back. GitHub Pages then serves it.

You do not need LaTeX installed locally. The Action does the compile in the cloud.

## One-time setup

Enable Pages once, Settings, Pages, Build and deployment, Deploy from a branch, pick `main` and the root folder. After that, pushing a `.tex` produces a `.pdf` next to it automatically.

## Structure

```
/                          ← latest resume: resume.tex + resume.pdf + index.html redirect
/roles/
  └── <company>-<role>/   ← version tailored for a specific application
        ├── resume.tex
        ├── resume.pdf     ← built by the Action
        └── index.html
```

## Live URL

`https://<your-github-username>.github.io/linkright-resume/`

Role-specific version:
`https://<your-github-username>.github.io/linkright-resume/roles/<company>-<role>/`

## Managed by

[`/linkright-push`](https://github.com/satvik-jain-iitd/linkright-skills), do not edit files here directly. All changes flow from `/linkright-sync` to `/linkright-push`. The only thing that runs in this repo is the compile workflow at `.github/workflows/compile.yml`.

---

*Part of the [LinkRight](https://github.com/satvik-jain-iitd/linkright-skills) AI career OS.*
