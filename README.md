# Font Awesome (slim)

A slim redistribution of [Font Awesome Free](https://fontawesome.com), containing
only the `css/` and `webfonts/` directories that Flarum uses at runtime. It exists
so installs do not have to carry the full upstream package, which ships every icon
as an individual SVG across several styles and totals well over 20,000 files — a
problem on shared hosting with inode limits, and for backup size and deploy time.

The assets here are **unmodified**. Only the unused directories (the SVG trees,
`js-packages`, `metadata`, `scss`, `sprites`, and so on) are left out. Versions
match upstream exactly, so `^7.0` resolves the same way it would against the full
package.

## Contents

- `css/` — the Font Awesome stylesheets, copied unchanged.
- `webfonts/` — the `.woff2` web fonts, copied unchanged.
- `LICENSE.txt` — the upstream Font Awesome Free licence, kept in full.

## Automation

This repository is generated. A scheduled job in
[flarum/framework](https://github.com/flarum/framework) checks for new upstream
releases and, when it finds one, triggers [the sync workflow](.github/workflows/sync.yml)
here, which copies the new assets in and tags the matching version. The workflow
can also be run manually from the Actions tab.

Do not commit to this repository by hand; changes will be overwritten on the next
sync.

## Need the full package?

If you depend on the files this subset leaves out (for example an extension that
reads the raw SVGs), require the upstream package directly:

```bash
composer require fortawesome/font-awesome
```

## Licence

Font Awesome Free is licensed under CC-BY-4.0 (icons), SIL OFL 1.1 (fonts) and MIT
(code). See [`LICENSE.txt`](LICENSE.txt). This repository redistributes the fonts
and stylesheets unchanged and retains the upstream licence and attribution in full.
