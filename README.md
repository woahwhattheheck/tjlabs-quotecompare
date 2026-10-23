# TJLabs QuoteCompare

Compare the supplier quotes you already have. See the cash required for your actual order after whole packs, minimums, discounts, freight, fees and stated tax. Unknown costs remain visible and currencies stay separate.

**[Open the free workbench](https://tjlabs-quotecompare.throwawaytempor.chatgpt.site)** · **[Read a finished fictional example](fictional-paperback-comparison.pdf)**

The example needs 250 paperbacks. A $4.40 unit quote has a 300-copy minimum and totals $1,450; the $5.00 unit quote totals $1,400 for 250. All suppliers and quote terms in the example are fictional.

## Use it with your assistant

Download [the complete 0.2.1 plugin](tjlabs-quotecompare-plugin-0.2.1.zip) and import it into a client that supports portable Agent Plugins ZIPs. It includes the hosted pack/minimum-order comparison tools and a local skill for straightforward quote rows. The local calculation scripts require a Node.js executor.

For a client that supports remote MCP connections directly, use:

- Transport: Streamable HTTP
- Server URL: `https://tjlabs-quotecompare.throwawaytempor.chatgpt.site/api/quote-mcp`
- Authentication: None
- Tools: `compare_supplier_quotes`, `export_quote_comparison`

Supply the required quantities and the quotes' pack sizes, prices, minimums, delivery, fees, discounts and tax treatment. Ask the assistant to compare the basket and export CSV. The package includes an exact input-format guide and fictional pack example.

Hosted tools send the supplied quote fields to the QuoteCompare service for calculation. The bundled local scripts calculate on the executor where you run them. Review the [privacy policy](https://tjlabs-quote-compare-desk.throwawaytempor.chatgpt.site/privacy.html) before submitting confidential material.

## Prefer a prepared comparison?

The separate **[$20 comparison preparation service](https://tjlabs-quote-compare-desk.throwawaytempor.chatgpt.site/offer.html)** covers one basket, up to three supplied quotes and twenty matched item lines. It provides a compact PDF, editable CSV, reusable workbench/project, one correction, and delivery within two business days after payment and readable sources. The offer page contains the current scope, checkout and intake instructions.

[Support](https://tjlabs-quote-compare-desk.throwawaytempor.chatgpt.site/support.html) · [Terms](https://tjlabs-quote-compare-desk.throwawaytempor.chatgpt.site/terms.html)

The comparison uses supplied quote data. Confirm product equivalence, stock and quote authenticity before ordering. The utility does not place orders.

## Release integrity

`tjlabs-quotecompare-plugin-0.2.1.zip` · 15,252 bytes  
SHA256: `e750b0a0a7abd28079d93fcce6fb948de34216b1b5b4f3abb7d70eff6446653e`
