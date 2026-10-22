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

Research and education only, not investment advice.
