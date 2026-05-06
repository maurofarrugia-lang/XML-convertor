# DubliNet Annex II XML to DOCX Converter

A GitHub-ready single-file HTML tool that converts DubliNet `TakeChargeRequestForm` XML into a Word report that follows the **ANNEX II** form layout.

## What this version fixes

- Uses the attached **official DubliNet Excel code tables** for field mappings.
- Resolves nationality more safely by checking DubliNet nationality and ISO/ICAO mappings before falling back to raw values.
- Resolves take-charge legal bases from the official Annex II / III workbook.
- Resolves member-state and country-like values using DubliNet member-state tables and ISO alpha-2 / alpha-3 interpretation where needed.
- Builds the DOCX output in the same order as the Annex II preview fields.
- Keeps unknown values visible instead of inventing mappings.

## Included files

- `index.html` — standalone converter, ready for GitHub Pages
- `README.md`
- `.gitignore`

## Usage

1. Open `index.html` in a browser.
2. Upload a DubliNet XML export.
3. Review the Annex II preview.
4. Click **Generate DOCX Report**.

## Notes

The page includes embedded mapping data so it can keep working after load without fetching the workbook again. The DOCX library still loads from public CDN fallbacks in the browser.
