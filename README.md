# Strategy Lab — algostrategylab.github.io

Source for the [Strategy Lab](https://algostrategylab.github.io/) site: systematic trading strategies
backtested properly, one article per strategy.

Plain static HTML, no build step. Each article is a folder with an `index.html`; charts and tables live
under `assets/`. The RSS feed at `feed.xml` carries quant content only.

Code for the backtests: [strategylab-core](https://github.com/AlgoStrategyLab/strategylab-core) (engine)
and one repo per strategy, e.g. [dual-momentum](https://github.com/AlgoStrategyLab/dual-momentum).

## Adding an article

1. Create `<slug>/index.html` (copy an existing one — it links `../style.css`).
2. Put charts in `assets/charts/` and table images in `assets/tables/`.
3. Add an entry to `index.html` and a new `<item>` at the top of `feed.xml`.

## Republishing to Medium

Medium's "import a story" tool fetches the article by its canonical URL and rewrites the HTML. Two
behaviours have cost real edits, so author around them:

- **`<ul>` and `<ol>` lists are silently dropped.** Anything that must survive the import belongs in
  a `<p>`. The repo links at the end of articles #2 and #3 vanished this way and had to be retyped
  into the published posts by hand. Write them as a sentence: `<p>Code: https://... and the shared
  engine: https://...</p>`.
- **The importer caches by canonical URL.** Fixing the source and re-importing returns the old copy;
  a `?r=2` cache-buster does not help. Get the source right *before* importing.

Also: Medium has no table support, so every table is rendered to a PNG by each strategy repo's
`site_build/make_tables.py`, and the alt text carries the numbers.

Research and education only, not investment advice.
