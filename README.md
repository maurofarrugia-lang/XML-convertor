# DubliNet XML to DOCX Converter — Annex II Edition

A browser-based XML to DOCX converter tailored for DubliNet `TakeChargeRequestForm` exports.

## What is different in this version

- Uses embedded official DubliNet code tables extracted from the provided workbook
- Formats output as an Annex II-style report for the submission of a take charge request
- Maps recognized code values for nationality, gender, marital status, and take charge legal basis
- Leaves unknown or unmatched values visible in raw form instead of guessing
- Includes a cleaner transmission and signature summary

## Files

- `index.html` — main browser app
- `.gitignore` — basic ignore rules
- `README.md` — usage notes

## How to use

1. Open `index.html` in a browser.
2. Upload a valid DubliNet XML file.
3. Review the Annex II preview.
4. Click **Generate DOCX Report**.

## Notes

This project loads the DOCX library from browser CDNs with fallback loading. If your environment blocks those CDNs, DOCX export will not be available until access is allowed.

The embedded mappings come from the supplied DubliNet code workbook. The visual output structure follows the supplied Annex II PDF layout.
