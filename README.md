# qalisander.github.io

Personal consulting site for Alisander Qoshqosh, a Rust and blockchain engineer. It is plain HTML/CSS with no build step.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole site |
| `style.css` | Styles, with light and dark mode |
| `favicon.svg` | Tab icon |
| `assets/alisander-qoshqosh-cv.pdf` | Downloadable CV |
| `.nojekyll` | Tells GitHub Pages to serve files as-is, without running Jekyll |
| `profile-readme/README.md` | Draft for the `qalisander/qalisander` profile repo. It is not part of the site. |

## Local preview

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

## Deploy

```bash
git init -b main && git add . && git commit -m "Initial site"
gh repo create qalisander.github.io --public --source=. --push
gh api -X POST repos/qalisander/qalisander.github.io/pages -f 'source[branch]=main' -f 'source[path]=/'
```

The site goes live at https://qalisander.github.io within about a minute.

## Custom domain (optional)

1. Add a `CNAME` file whose only content is the domain, for example `alisander.dev`.
2. At the registrar, create A records for `@` pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153` and `185.199.111.153`, plus a CNAME record for `www` pointing to `qalisander.github.io`.
3. Go to Settings → Pages → Custom domain, then tick **Enforce HTTPS** once the certificate has been issued.
4. Update `canonical` and `og:url` in `index.html`.
