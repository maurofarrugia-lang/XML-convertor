# XML to DOCX Report Converter

A browser-based XML to DOCX converter with a polished interface, XML validation, structure preview, and report-style Word export.

## Features

- Upload XML files with click or drag-and-drop
- Validate XML before conversion
- Preview XML structure in the browser
- Generate a polished DOCX report
- Include XML attributes in the report
- Include an executive summary table
- Optionally append raw XML as an appendix
- Uses browser-side DOCX generation with CDN fallback loading

## Files

- `index.html` — main app
- `.gitignore` — basic ignore rules for GitHub repo hygiene

## How to use

1. Open `index.html` in a browser.
2. Upload a valid `.xml` file.
3. Review the preview and options.
4. Click **Generate DOCX Report**.

## Deploy on GitHub Pages

1. Create a new GitHub repository.
2. Upload the files from this folder.
3. Commit and push.
4. In GitHub, go to **Settings → Pages**.
5. Set the source branch to your main branch and root folder.
6. Save, then open the generated GitHub Pages URL.

## Notes

This project loads the DOCX library from browser CDNs. If your network blocks those CDNs, DOCX export may not be available until access is allowed.
