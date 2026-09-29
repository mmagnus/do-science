# Do Science! — do-science.org

Static website of **Do Science!**, the science club at Biocentrum Ochota, Warsaw:
lectures and informal discussions over coffee or beer with excellent scientists, and SciEvents,
a shared calendar of bioscience events in Warsaw.

Plain HTML/CSS/JS, no build step. Hosted on GitHub Pages.

## Files

```
index.html              the whole site (styles and script inline)
assets/banner.webp      hero illustration
assets/banner.jpg       same image for social-media previews
assets/logo.webp        logo
assets/favicon-32.png   browser tab icon
assets/apple-touch-icon.png
CNAME                   custom domain for GitHub Pages
.nojekyll               serve files as-is
```

## Editing the meeting archive

Meetings live in the `TALKS` array near the bottom of `index.html`. One line per meeting:

```js
{d:"2017-09-28", n:"", who:"Dominika Nowis", aff:"CeNT UW", title:"The role of arginase-1 in antitumor immune response", kind:"Lecture"},
```

`d` is the date (YYYY-MM-DD), `n` the original meeting number (optional), `kind` one of
`Lecture`, `Nobel laureate`, `Opening`, `Journal club`, `Mini-course`, `Symposium`, `Trip`, `Online`,
`RNA Club × Do Science!`. The list is sorted automatically, newest first.

The "Next lecture" box is in the `#format` section: edit the date and text there.

## Local preview

```
python3 -m http.server 8000
```
then open http://localhost:8000.

## Publishing on GitHub Pages with do-science.org

1. Create a repository (e.g. `do-science/do-science.org`) and push these files to the `main` branch.
2. Repository → Settings → Pages → Source: *Deploy from a branch*, Branch: `main`, folder `/ (root)`.
3. Custom domain: `do-science.org` (the `CNAME` file sets this already). Tick **Enforce HTTPS** once the certificate is issued.
4. At the domain registrar, set DNS:

| Type  | Name | Value                  |
|-------|------|------------------------|
| A     | @    | 185.199.108.153        |
| A     | @    | 185.199.109.153        |
| A     | @    | 185.199.110.153        |
| A     | @    | 185.199.111.153        |
| AAAA  | @    | 2606:50c0:8000::153    |
| AAAA  | @    | 2606:50c0:8001::153    |
| AAAA  | @    | 2606:50c0:8002::153    |
| AAAA  | @    | 2606:50c0:8003::153    |
| CNAME | www  | `<your-github-username>.github.io` |

DNS changes can take up to 24 h. Optionally verify the domain in your GitHub account settings
(Settings → Pages → Add a domain) to protect it from takeover.

## Contact

doscience.iimcb@gmail.com
