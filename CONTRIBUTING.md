# Contributing to Hondabase articles

This repository holds the article content for https://hondabase.com.

- **How articles are formatted:** see [docs/article-format.md](docs/article-format.md).
- **Types and categories:** see [README.md](README.md).
- **Markdown basics:** see [markdown-cheat-sheet.md](markdown-cheat-sheet.md).

In short: an article is a folder `<type>/<category>/<slug>/<slug>.md` with its images
beside it. Write for a Honda owner or DIY mechanic on a phone in the garage. Keep
terminology consistent, structure with clear headings, and link to related Hondabase
articles rather than external forums.

## Porting archived wiki articles

A port must be source-faithful without preserving the wiki's poor presentation. Rewrite
and reorganize the material, but do not invent technical explanations, fill gaps with
guesses, silently correct suspicious values, or promote old community advice into a
current recommendation.

Before submitting a port:

1. Compare the finished Markdown with the raw archived page, not only the generated draft.
2. Verify every retained table, formula, pinout, part number, address, unit, and asset.
3. Compare the archive attachment list with the article bundle. Bring every useful,
   recovered image and download with the port, then test its rendered asset URL.
4. Remove broken attachment links. If a referenced file was not recovered and matters to
   the article, say so explicitly.
5. Preserve uncertainty and explicitly note contradictions or questionable source values.
6. Label old software behavior, supplier numbers, and tuning settings as historical.
7. Use only renderer-supported Markdown and documented widgets.
8. Run `php artisan app:lint-articles` from the Hondabase site checkout.

A passing linter confirms structure and local image references; it does not verify
download URLs, technical accuracy, or source fidelity.
