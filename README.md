# Squid BOM Bridge for Power Advisor

Convert HPE OCA BOM exports (.xlsx, .csv or pasted cells) into OCA JSON files that HPE Power Advisor can import.

**Use it in your browser:** https://dsaleeb.github.io/squid-bom-bridge/

Or download `Squid-BOM-Bridge.html` from the [latest release](https://github.com/dsaleeb/squid-bom-bridge/releases/latest) and open it locally. It is a single HTML file, and your BOMs never leave your machine.

## What it does

- Reads OCA configuration exports: configuration name, UCID, and the Hardware, Software and Support sections.
- Uses the CTO server line as the model, and lists the rest as parts in OCA's JSON structure.
- Sorts every line so you can see what is exported: powered hardware, non-powered accessories (rails, bezels, cables, heat sinks), software and support.
- Leaves out localization and option-code lines such as `P52534-B21 ABA`, which OCA's JSON has no field for.
- Loads several BOMs at once and saves them as one combined file, or as one file per configuration.

## How to use it

1. Drop one or more OCA exports onto the page, or paste rows copied from Excel.
2. Review the lines. Tick or untick any line to override the default.
3. Under **OCA header**, set your user ID and input voltage. Your browser remembers them.
4. Under **Export**, tick the configurations you want and click **Save**.
5. In HPE Power Advisor, import the file as an OCA JSON file.

## Notes

- Reading .xlsx files needs an internet connection the first time, to load the spreadsheet reader. Pasting rows works offline.
- HPE does not publish the OCA JSON schema. The structure here is matched to real OCA exports. For combined files, if Power Advisor rejects the import, change **Solution type** under OCA header and save again.

## Version

1.0.0

---

Created by Dan Saleeb · [github.com/dsaleeb](https://github.com/dsaleeb)
