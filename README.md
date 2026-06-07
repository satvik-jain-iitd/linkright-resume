# Resume, versioned by LinkRight

This repo hosts my live resume, one version per application, all generated and published by [LinkRight](https://github.com/satvik-jain-iitd/linkright-skills), the career OS I built.

Nothing here is written by hand. Each resume is tailored to a specific job description by the LinkRight pipeline, which guarantees it never invents a metric, then published here automatically. The default format is LaTeX compiled to PDF; HTML is optional.

## How it works

`/linkright-push` does the publishing. On each run it:

1. Writes the tailored resume as a `.tex` file (LaTeX, the default), or HTML if that path was chosen.
2. For LaTeX, also writes a small `index.html` that redirects to the compiled `resume.pdf`.
3. Commits with the tag `<company>-<role>-<date>` and pushes here.
4. On push, a GitHub Action compiles every `.tex` to PDF with XeLaTeX and commits the PDF back. GitHub Pages serves it.

No local LaTeX install needed. The compile runs in the cloud, in the Action.

## One-time setup

Enable Pages once: Settings, Pages, Build and deployment, Deploy from a branch, pick `main` and the root folder. After that, pushing a `.tex` produces a `.pdf` next to it automatically.

## Structure

```
/                         # latest resume: resume.tex + resume.pdf + index.html redirect
/roles/
  <company>-<role>/       # a version tailored for one application
        resume.tex
        resume.pdf        # built by the Action
        index.html
```

## Live URL

`https://<github-username>.github.io/linkright-resume/`

Role-specific version: `https://<github-username>.github.io/linkright-resume/roles/<company>-<role>/`

## Managed by the system

Do not edit files here directly. Everything flows from `/linkright-sync` to `/linkright-push`. The only thing that runs in this repo is the compile workflow at `.github/workflows/compile.yml`.

Part of [LinkRight](https://github.com/satvik-jain-iitd/linkright-skills), a local-first career OS.
