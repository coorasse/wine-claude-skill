# Sources for wine research

A field guide to where reliable wine information lives, what each source is good for, and how to
query it. Read this when the initial searches do not surface the producer, when the region is
unfamiliar, or when prices are hard to find.

## Producer facts

| Source | Best for | Notes |
| --- | --- | --- |
| Producer's official site | Grapes, vineyard, ageing, alcohol, history | Look for "technical sheet", "scheda tecnica", "fiche technique", "ficha técnica", often a PDF |
| Regional consortium / appellation body | Rules of the appellation, allowed grapes, ageing minimums | e.g. consorziobarolobarbaresco.com, vins-bourgogne.fr, riojawine.com |
| Wikipedia | Overview of a famous estate or appellation | Verify anything specific on the producer's site |
| Importer or distributor pages | Estates without a good website | Often reproduce the technical sheet |

Query patterns:

- `"<producer>" sito ufficiale` / `"<producer>" official website`
- `"<producer>" "<wine>" scheda tecnica pdf`
- `"<producer>" "<wine>" technical sheet`

## Reviews, scores and tasting notes

| Source | Coverage | Access |
| --- | --- | --- |
| Vivino | Almost every wine; community ratings and notes; price hints | Free, search results show average rating |
| Wine-Searcher | Aggregated critic scores, prices | Free tier shows some prices |
| Decanter | European wines, vintage reports | Partially paywalled |
| Wine Spectator, Wine Advocate, Vinous, Jancis Robinson | Detailed scores by vintage | Mostly paywalled, but scores appear in search snippets and on retailer pages |
| James Suckling | Broad coverage, scores by vintage | Scores visible on retailers |
| Gambero Rosso, Slow Wine, Bibenda, Doctor Wine | Italian wines, Tre Bicchieri and similar awards | Search `"<wine>" <vintage> gambero rosso` |
| Falstaff, Vinum | German, Austrian, Swiss wines | Scores visible on retailer pages |
| Guía Peñín | Spanish wines | Scores visible on retailer pages |
| CellarTracker | Consumer notes on drinking windows and how a wine is evolving | Useful for older vintages |

Retailer product pages (Tannico, Callmewine, Millesima, Vinatis) usually list several critic scores
per vintage in one place, which saves searches.

## Vintage reports

When there is no wine-specific vintage note, use the region and year:

- Decanter and Wine-Searcher publish vintage charts by region.
- Consortia and regional bodies publish harvest reports (`vendemmia <year> Barolo`, `millésime
  <year> Bordeaux`, `cosecha <year> Rioja calificación`).
- Rioja and Ribera del Duero publish an official vintage rating (Excelente, Muy Buena, Buena).
- For Champagne and Port, a declared vintage is itself a signal; say whether the year was widely
  declared.

Always label the result as "region-level" when it is not about the specific wine.

## Prices in EUR on the European market

| Source | Notes |
| --- | --- |
| wine-searcher.com | Aggregator; append `EUR` or search `site:wine-searcher.com <wine> <vintage>`. Shows a global average and per-merchant prices; filter to EU merchants when possible |
| Vivino | Shows a price per country; the Vivino price is a market indication, not a shop offer |
| Tannico, Callmewine, xtraWine, Vino.com, Bernabei | Italian retailers, EUR |
| Vinatis, Millesima, Lavinia, Idealwine (auction) | French retailers, EUR |
| Hawesko, Weinco, Vicampo, Wein.de | German retailers, EUR |
| Uvinum / Drinks&Co, Vinissimus, Bodeboca | Spanish retailers, EUR |
| Flaschenpost, Coop Mondovino, Denner, Vinatis.ch | Swiss retailers, CHF (state it and give an approximate EUR conversion only if a rate is checked) |
| Berry Bros, Farr Vintners, Justerini & Brooks | UK, GBP; useful for fine wine but not EU market |

Rules of thumb:

- Quote the vintage the user asked about. If it is sold out, say "vintage <year> not currently
  listed" and give the nearest vintage with its year.
- Distinguish retail (shop price, tax included) from ex-cellar, auction hammer and en primeur.
- Bottle size matters: magnums and halves skew the range; report 750 ml unless the label says
  otherwise.
- Supermarket wines (Tavernello, Lidl and Aldi private labels, Coop/Migros own brands) rarely
  appear on aggregators; search the supermarket's own site or a price comparison site of that
  country.
- If only one price point exists, present it as a single data point, not a range.
