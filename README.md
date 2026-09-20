# wine-claude-skill

A [Claude skill](https://support.claude.com/en/articles/12512180-use-skills-in-claude) that identifies
a wine from a photo of its label or from a name and vintage, researches it on the web, and returns a
short, sourced wine card: producer, wine, tasting notes, vintage characteristics, food pairings and
the current price on the European market.

Built to be used from a phone in a wine shop or at a restaurant table.

## What you get

Send Claude a picture of a bottle, or write something like "Tignanello 2019" or "that Barolo from
Conterno", and the skill answers with:

- **Identification**: producer, wine, appellation, vintage, style, and how confident the match is
  when the label is hard to read.
- **Producer**: who they are, where, and a link to the official website.
- **The wine**: grapes, vineyard, vinification and ageing, from the producer's technical sheet.
- **Tasting notes and scores**: attributed to the critic or the producer who wrote them.
- **Vintage**: what is documented about that vintage of that wine, or of the region in that year,
  clearly labelled as one or the other.
- **When to drink**: the recommended window in calendar years when the vintage is known, otherwise
  in years from the harvest.
- **Food pairings**.
- **Price in EUR**: a range for a 750 ml bottle with individual price points and links to the shops
  or aggregators where they were found, dated.
- **Sources**: every link actually used.

## How it works

The skill is a single `SKILL.md` file with instructions, plus a `references/sources.md` field guide
of trustworthy wine sources (producer sites, consortia, critics, vintage reports, European retailers
and aggregators) and how to query them.

The central rule is that nothing is answered from memory. Claude reads the label, forms search
queries, and every fact, score and price in the card comes from a web search done during the
conversation. When something cannot be found, the card says "not found" instead of filling the gap
with a plausible guess. If web search is not available, the skill says so and stops at what the
label itself shows.

The answer is written in the language the user used.

## Installation

### Claude app (web, desktop, iOS, Android)

1. Download the latest `wine-identifier.skill` from the
   [releases](https://github.com/coorasse/wine-claude-skill/releases) page, or build it yourself
   (see below).
2. On claude.ai open **Settings → Capabilities → Skills**, click **+**, then **Upload a skill** and
   select the file.
3. The skill is now available in every conversation, including the mobile apps, and syncs to
   Claude Code sessions signed in with the same account.

To build the file yourself, zip the repository folder so that the archive contains
`wine-identifier/SKILL.md` and `wine-identifier/references/sources.md`:

```sh
git clone https://github.com/coorasse/wine-claude-skill.git wine-identifier
zip -r wine-identifier.skill wine-identifier -x "wine-identifier/.git/*"
```

### Claude Code only

Clone the repository into your personal skills folder:

```sh
git clone https://github.com/coorasse/wine-claude-skill.git ~/.claude/skills/wine-identifier
```

Or, inside a project, into `.claude/skills/wine-identifier`.

## Usage examples

- A photo of a bottle, no text.
- "What is this wine and is it worth 45 euros?" with a photo of the shelf tag.
- "Sassicaia 2018: how is the vintage and what should I cook with it?"
- "Two bottles of Chablis in the photo, which one should I pick for oysters?"

## Limitations

- Prices are what the retailers listed at the time of the search. They vary by country, shop and
  bottle size, and the skill reports them as data points, not as a valuation.
- Small producers with no web presence may yield a card with several "not found" fields. That is
  intended.
- Paywalled critic reviews are only used as far as their scores and snippets are publicly visible.

## Contributing

Open an issue or a pull request. Keep `SKILL.md` short and explain the *why* of every instruction;
the reference file is the place for lists of sources.
