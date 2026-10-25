# TJLabs QuoteCompare

Compare the supplier quotes you already have. See the cash required for your actual order after whole packs, minimums, discounts, freight, fees and stated tax. Unknown costs remain visible and currencies stay separate.

**[Open the free workbench](https://tjlabs-quotecompare.throwawaytempor.chatgpt.site/)** · **[Download the free plugin](https://raw.githubusercontent.com/woahwhattheheck/tjlabs-quotecompare/f03435d0b4b11693d3a95351f006f65fc0c898c1/tjlabs-quotecompare-plugin-0.2.1.zip)** · **[Download the fictional comparison PDF](https://raw.githubusercontent.com/woahwhattheheck/tjlabs-quotecompare/f03435d0b4b11693d3a95351f006f65fc0c898c1/fictional-paperback-comparison.pdf)**

The example needs 250 paperbacks. A $4.40 unit quote has a 300-copy minimum and totals $1,450; the $5.00 unit quote totals $1,400 for 250. All suppliers and quote terms in the example are fictional.

## Use it with your assistant

Download the complete 0.2.1 plugin above and import it into a client that supports portable Agent Plugins ZIPs. It includes the hosted pack/minimum-order comparison tools, a local skill, complete calculation scripts and input guides.

For a client that supports remote MCP connections directly, use:

- Transport: Streamable HTTP
- Server URL: `https://tjlabs-quotecompare.throwawaytempor.chatgpt.site/api/quote-mcp`
- Authentication: None
- Tools: `compare_supplier_quotes`, `export_quote_comparison`

Supply the required quantities and the quotes' pack sizes, prices, minimums, delivery, fees, discounts and tax treatment. Ask the assistant to compare the basket and export CSV. The package includes an exact input-format guide and fictional pack example.

Hosted tools process the supplied quote fields on the QuoteCompare service. The bundled local scripts calculate where you run them. Review the [privacy policy](https://tjlabs-quote-compare-desk.throwawaytempor.chatgpt.site/privacy.html) before submitting confidential material.

## Run the local calculation

The bundled local script handles straightforward quantity-times-unit-price rows, with its documented discount and tax basis. Use the hosted tools or free workbench for whole packs, minimum quantities, order increments, explicit unit conversions and separate line/order discounts.

Unzip the package and read `skills/compare-quotes/references/input-format.md`. From `skills/compare-quotes`, run:

```sh
node scripts/compare-quotes.mjs input.json --output comparison.json
```

For a source CSV using the documented columns:

```sh
node scripts/compare-quotes.mjs quotes.csv --csv --output comparison.json
```

The scripts require Node.js 18 or later, with no external packages or network calls. Keep missing prices, freight and tax information distinct from explicit zero. Retain each source quote's units, quantities and terms when preparing the input.

## Prefer a prepared comparison?

The separate **[$20 comparison preparation service](https://tjlabs-quote-compare-desk.throwawaytempor.chatgpt.site/offer.html)** covers one basket, up to three supplied quotes and twenty matched item lines. It provides a compact PDF, editable CSV, reusable workbench/project, one correction, and delivery within two business days after payment and readable sources. The offer page contains the current scope, checkout and intake instructions.

[Support](https://tjlabs-quote-compare-desk.throwawaytempor.chatgpt.site/support.html) · [Terms](https://tjlabs-quote-compare-desk.throwawaytempor.chatgpt.site/terms.html)

The comparison uses supplied quote data. Confirm product equivalence, stock and quote authenticity before ordering. The utility does not place orders.

## Download integrity

The direct downloads above are pinned to the original package commit, so both links retain the reviewed bytes.

| Download | Bytes | SHA256 |
| --- | ---: | --- |
| tjlabs-quotecompare-plugin-0.2.1.zip | 15,252 | `e750b0a0a7abd28079d93fcce6fb948de34216b1b5b4f3abb7d70eff6446653e` |
| fictional-paperback-comparison.pdf | 46,976 | `47fad90ddff5ebff030e594d412c5d5042d45d1486112d1168a1b09ded583cd0` |
