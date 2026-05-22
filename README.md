# Resume — Versioned with LinkRight

This repository hosts a versioned, publicly accessible resume published via [LinkRight](https://github.com/satvik-jain-iitd/linkright-skills).

## How it works

Every time `/linkright-push` runs, it:
1. Validates the resume HTML (ATS scan + width check)
2. Generates a PDF alongside the HTML
3. Commits with a tag: `<company>-<role>-<date>`
4. Pushes to this repo → GitHub Pages serves it instantly

## Structure

```
/                          ← latest resume (index.html)
/roles/
  └── <company>-<role>/   ← version tailored for a specific application
        ├── index.html
        └── resume.pdf
```

## Live URL

`https://<your-github-username>.github.io/linkright-resume/`

Role-specific version:
`https://<your-github-username>.github.io/linkright-resume/roles/<company>-<role>/`

## Managed by

[`/linkright-push`](https://github.com/satvik-jain-iitd/linkright-skills) — do not edit files here directly. All changes flow from `/linkright-sync` → `/linkright-push`.

---

*Part of the [LinkRight](https://github.com/satvik-jain-iitd/linkright-skills) AI career OS.*
