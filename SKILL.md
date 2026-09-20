---
name: wine-identifier
description: >-
  Identify a wine from a photo of its label (front, back, or capsule) or from a name and vintage,
  then research it on the web and report verified facts only: the producer (with official website),
  the wine itself (grapes, region, appellation, style, ageing), tasting notes, food pairings, the
  characteristics of that specific vintage when they are documented, and the current bottle price on
  the European market in EUR with source links. Use this skill whenever the user shares a picture of
  a bottle or a wine label, names a wine (even misspelled or partial, e.g. "Tignanello 2019",
  "that Barolo from Conterno"), asks what a wine is, what it costs, what to pair it with, whether a
  vintage is good, or asks for help choosing at a restaurant, wine shop, or supermarket. It also
  fits when the user only sends a photo with no text. Never answer from memory alone: the skill
  exists so that every fact and price comes from a live web search.
---

# Wine identifier

Turn a label photo or a "name + year" into a reliable, sourced wine card. The user is often standing
in a shop or at a table with their phone, so speed and honesty matter more than completeness: a short
card with verified facts beats a long one with guesses.

## Core rule: no invented information

Everything in the answer comes from a web search done during this conversation, or from what is
visibly printed on the label. You have a lot of wine knowledge in memory, and much of it is roughly
right, but prices, vintage quality, scores and producer details drift or are simply wrong for
smaller estates. Memory is fine for forming search queries and interpreting results, not as a source.

Concretely:

- Prices are quoted only when found on a page you actually opened or that appeared in search
  results with the amount visible. Say which shop or aggregator and when (today's date).
- Vintage characteristics are reported only when a source talks about that vintage of that wine
  (producer's technical sheet, a critic's review) or, as a fallback, about that vintage in that
  region (a vintage report). Label which of the two you found. If neither exists, say so instead
  of describing the wine generically as if it were vintage-specific.
- Scores, awards and quotes are attributed to their source with a link.
- If web search is not available in the current environment, tell the user plainly that you cannot
  verify anything, offer what you can read from the label, and stop there. Do not give prices.
- When something could not be found, write "not found" for that field. An honest gap is useful;
  a plausible filler is harmful, because the user may act on it (buy, gift, cellar).

## Step 1: Identify the wine

From a photo, read every text element and note what you are sure of and what you are guessing:

- Producer or estate name (often the largest text, or the signature at the bottom).
- Wine name, cru, vineyard, or fantasy name.
- Appellation and classification (DOCG, DOC, AOC, AOP, DO, QbA, Prädikat, Riserva, Gran Reserva,
  Grand Cru, and so on).
- Vintage. If there is no vintage it may be a non-vintage sparkling wine or the year is on the
  back label or the capsule. Say when the vintage is missing.
- Alcohol, bottle size, importer, lot codes, and the back label text, which often names the
  grapes and the ageing.

Handle common pitfalls:

- Negociants, cooperatives and supermarket private labels: the bottler line ("imbottigliato da",
  "mis en bouteille par", "embotellado por") tells you who really made it.
- Same wine name from several producers (Barolo, Chablis, Rioja): the producer is the key, the
  appellation alone is not enough.
- Blurry or partial photos: state what you could read, search with that, and if the match is
  uncertain present the best candidate with your confidence level and ask for a second photo of
  the front or back label. One short clarifying question is fine; a long interrogation is not.
- Text input with typos ("Sassicaja 2018"): search the corrected spelling and confirm it in the
  answer.

From text, do the same: extract producer, wine, vintage, and search.

## Step 2: Research on the web

Run several focused searches rather than one broad one. Typical sequence, in order of value:

1. `"<producer>" "<wine name>" <vintage>` to confirm the wine exists and find the producer's page.
2. The producer's official site: technical sheet (grapes, vineyard, vinification, ageing, alcohol),
   history, location, size, and the page for this specific wine. Prefer it over any third party
   for the facts about the wine itself.
3. Reviews and scores for this vintage: Decanter, Wine Spectator, Wine Advocate, Vinous, James
   Suckling, Jancis Robinson, Gambero Rosso, Falstaff, Guía Peñín, and Vivino community notes.
   Two or three sources are enough.
4. Vintage report for the region and year when no wine-specific vintage information exists.
5. Prices in EUR on the European market: wine-searcher.com (set to EUR or a EU country), Vivino,
   and European retailers such as Tannico, Callmewine, xtraWine, Vinatis, Millesima, Lavinia,
   Uvinum, Hawesko, Weinco, Berry Bros (UK, note it is GBP). Collect two to four price points for
   the exact vintage in 750 ml. If the exact vintage is not on sale, say so and give the closest
   vintage available, clearly labelled.

See `references/sources.md` for what each source is good for and how to query it. Read it when the
first searches do not land or the wine is from a less common region.

Stop researching once the card can be filled with sourced facts. Five to eight searches is a normal
budget; more than that rarely adds value and slows down someone waiting in a shop.

## Step 3: Write the card

Answer in the language the user wrote in (or, for a photo with no text, the language of the
conversation so far). Keep the card readable on a phone: short paragraphs, no wide tables, links
as plain markdown links. Use this structure and keep the headings:

```
## <Producer> – <Wine name> <vintage>
One line: appellation, region, country, colour and style (e.g. dry red, brut sparkling), alcohol.
Confidence in the identification if it is not certain, and what was read from the label.

### Producer
Two to four sentences: who they are, where, since when, size or philosophy, anything notable.
Official website link. Other useful links (Wikipedia, importer, region consortium) only if real.

### The wine
Grapes and blend, vineyard or cru, vinification and ageing, typical style. Source: producer's
technical sheet or the source used.

### Tasting notes
A short sourced description. Quote or paraphrase a critic or the producer and attribute it.
Scores with source and vintage, if found.

### Vintage <year>
What is known about this vintage of this wine, or of the region in that year, clearly marked as
one or the other. Drinking window if a source gives one. "Not found" if nothing reliable exists.

### Food pairings
Three to six pairings, favouring the producer's or a critic's suggestions, and local cuisine of
the wine's region when it is a traditional style. Keep generic pairings short.

### Price (Europe)
A range in EUR for a 750 ml bottle of this vintage, then the individual price points as
"shop – price – link". State the date. Mention if the wine is out of stock everywhere, only at
auction, or only found in another vintage.

### Sources
The links actually used, one per line.
```

Omit a section only when there is genuinely nothing to say and you have already noted "not found"
where the user would expect information (vintage and price are the ones people ask about most).

## Tone

Be a knowledgeable friend, not a wine magazine. Plain words, no purple prose, no invented tasting
poetry. If the wine is cheap and simple, say so kindly; if it is a bargain or overpriced compared to
the price points found, it is useful to point that out with the numbers that support it.
