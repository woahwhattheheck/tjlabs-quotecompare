# TJLabs QuoteCompare

Compare the supplier quotes you already have. See the cash required for your actual order after whole packs, minimums, discounts, freight, fees and stated tax. Unknown costs remain visible and currencies stay separate.

**[Open the free workbench](https://tjlabs-quotecompare.throwawaytempor.chatgpt.site/)** · **[Download the free plugin](https://raw.githubusercontent.com/woahwhattheheck/tjlabs-quotecompare/0d41c121a960b507fd5b916ba8ff05d6f9eae446/tjlabs-quotecompare-plugin-0.3.1.zip)** · **[Download the fictional comparison PDF](https://raw.githubusercontent.com/woahwhattheheck/tjlabs-quotecompare/f03435d0b4b11693d3a95351f006f65fc0c898c1/fictional-paperback-comparison.pdf)**

The example needs 250 paperbacks. A $4.40 unit quote has a 300-copy minimum and totals $1,450; the $5.00 unit quote totals $1,400 for 250. All suppliers and quote terms in the example are fictional.

## Use it with your assistant

Download the complete 0.3.1 plugin above and import it into a client that supports portable Agent Plugins ZIPs. It includes local whole-pack and minimum-order calculations, an editable offline workbench, the existing unit-price workflow, and the optional hosted comparison tools. The calculation scripts and input guides are included.

For a client that supports remote MCP connections directly, use:

- Transport: Streamable HTTP
- Server URL: `https://tjlabs-quotecompare.throwawaytempor.chatgpt.site/api/quote-mcp`
- Authentication: None
- Tools: `compare_supplier_quotes`, `export_quote_comparison`

Supply the required quantities and the quotes' pack sizes, prices, minimums, delivery, fees, discounts and tax treatment. Ask the assistant to compare the basket and export CSV. The package includes an exact input-format guide and fictional pack example.

Hosted tools process the supplied quote fields on the QuoteCompare service. The bundled local scripts calculate where you run them. Review the [privacy policy](https://tjlabs-quote-compare-desk.throwawaytempor.chatgpt.site/privacy.html) before submitting confidential material.

## Compare whole orders on your device

Unzip the package and read `skills/compare-quotes/references/pack-input-format.md`. From `skills/compare-quotes`, calculate the basket:

```sh
node scripts/compare-basket.mjs basket.json --out comparison
```

The new `comparison` folder contains three files:

| File | Use |
| --- | --- |
| `workbench.html` | Open this first. Review supplier terms, change quantities, recalculate, export CSV, or print a PDF in your browser. |
| `project.json` | Save and reopen the complete source-bearing input. |
| `comparison.csv` | Share a compact snapshot of calculated supplier and item rows with source references. |

The workbench calculates locally without a server or installation. Use **Download project** to retain edits, then import the saved project to resume. Editing the CSV snapshot does not recalculate the order. The CSV's `line_unit_cost_excl_order_charges` describes the cost per requested unit after the line discount, before the separate order discount, freight, fees and tax.

To enter quotes in a spreadsheet, generate the basket template and supply the comparison date explicitly:

```sh
node scripts/compare-basket.mjs --template quotes.csv
node scripts/compare-basket.mjs quotes.csv --csv --as-of 2026-10-26 --out comparison
```

Use the real comparison date and preserve the original quote validity dates. The command requires a new output folder, so it preserves prior comparisons. Without `--out`, it writes the complete calculation as JSON to standard output.

Try the **[fictional cafe comparison ZIP](https://raw.githubusercontent.com/woahwhattheheck/tjlabs-quotecompare/c914c4335ba7db7549016445e11cb09be7f5028f/QC21_Cafe_Quote_Comparison.zip)**. Unzip its four files and open `workbench.html`. The cafe needs 300 cups. Birch supplies 360 for $45.36, the lowest fully priced offer; Cedar's $27.00 quote still has unknown freight. The guide explains the pack minimums, two discounts, tax and the $18.36 freight break-even point. All suppliers and quote terms are fictional.

For straightforward quantity-times-unit-price rows, the original format and command remain available. Read `references/input-format.md` and run:

```sh
node scripts/compare-quotes.mjs input.json --output comparison.json
node scripts/compare-quotes.mjs quotes.csv --csv --output comparison.json
```

Both local scripts require Node.js 18 or later, with no external packages or network calls. Keep the basket and unit-price input formats distinct. Preserve unknown prices, freight and tax treatment as unknown; use zero only when the source establishes zero.

## Support

[Support](https://tjlabs-quote-compare-desk.throwawaytempor.chatgpt.site/support.html) · [Terms](https://tjlabs-quote-compare-desk.throwawaytempor.chatgpt.site/terms.html)

The comparison uses supplied quote data. Confirm product equivalence, stock and quote authenticity before ordering. The utility does not place orders.

## Download integrity

The downloads are pinned to their package commits. Version 0.3.1 points the plugin listing to the utility information page and keeps its skill focused on the supplied-quote comparison workflow. The original [0.2.1 plugin](https://raw.githubusercontent.com/woahwhattheheck/tjlabs-quotecompare/f03435d0b4b11693d3a95351f006f65fc0c898c1/tjlabs-quotecompare-plugin-0.2.1.zip) and [0.2.1 release](https://github.com/woahwhattheheck/tjlabs-quotecompare/releases/tag/v0.2.1) remain available for existing installations. The paperback PDF link retains its original reviewed bytes.

| Download | Bytes | SHA256 |
| --- | ---: | --- |
| tjlabs-quotecompare-plugin-0.3.1.zip | 57,499 | `afe03bf38c03d684762e5209a653bd49ba0f5482b62ab4bc079eed6b897b252b` |
| QC21_Cafe_Quote_Comparison.zip | 24,558 | `36120e716aa3b0db2ddaaf1a9c5f6c95d2d5939cb1eae411035748f9e809c434` |
| fictional-paperback-comparison.pdf | 46,976 | `47fad90ddff5ebff030e594d412c5d5042d45d1486112d1168a1b09ded583cd0` |
