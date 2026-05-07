# DubliNet XML Converter

A single-file HTML converter for DubliNet XML that supports template-based export to DOCX, HTML, and attachment-aware XML.

## What this tool does

The converter reads DubliNet XML files, applies embedded DubliNet code-table mappings, renders a DubliNet-style preview, and exports one or more output formats.

Supported output targets:
- DOCX report output
- Styled HTML output that also opens as a rendered preview in a new browser tab when generated
- XML output with generated attachment elements for validated Base64 PDF payloads

## Main features

- Template chooser for DubliNet-style output layouts
- Official mapping support for nationality, legal base, member state, and related code tables
- Preview panel that shows detected XML content in template order where possible
- Base64 PDF validation workflow for XML payloads that contain embedded PDF documents
- In-app README viewer with fallback to an embedded copy of this README

## How to use the converter

### 1. Open the tool

Open `index.html` in a modern browser.

### 2. Upload an XML file

Use the XML upload area to select or drag and drop a DubliNet XML file.

### 3. Choose the output template

Pick the target DubliNet template from the template selector. The preview and default output file name update when the template changes.

### 4. Choose the output format

Choose one of the following:
- DOCX
- HTML
- DOCX + HTML

If the `Export XML with validated Base64 PDF attachment elements` checkbox is enabled, the converter also exports an XML file containing generated attachment elements.

### 5. Review the preview

The preview panel shows:
- detected XML structure
- mapped DubliNet fields when available
- validated PDF attachments found in Base64 form

### 6. Generate the outputs

Click `Generate Output`. The converter downloads the requested files automatically.

## Base64 PDF attachment workflow

If the uploaded XML contains a Base64-encoded PDF payload, the converter can:
- decode the Base64 string to binary
- validate that the decoded binary starts with `%PDF`
- re-encode the same binary content back to Base64 without altering the PDF bytes
- generate a well-formed XML export containing attachment elements with:
  - `fileName`
  - `mimeType`
  - `encoding`
  - `sourcePath`
  - `content`

The generated XML attachment export is appended under a `generatedAttachments` element.

## How to read the README inside the converter

The converter includes a `Read README` button.

When used inside the repo or a hosted copy, the converter first tries to read `README.md` directly. If that is not available, it falls back to an embedded copy of the README so the instructions are still available offline.

The `Load README File` button can also read an uploaded `.md` or `.txt` file and display it inside the converter.

## Files included in the GitHub package

- `index.html` — main standalone converter
- `README.md` — usage instructions
- `.gitignore`

## Deployment notes

The ZIP package is prepared for GitHub upload. After extraction, upload the repo contents to GitHub or place them on a static host.

The HTML file contains the embedded code mappings and README fallback content. DOCX export still requires the public DOCX library to load in the browser.

## Limitations

- The strongest semantic XML mapping is still the dedicated DubliNet take-charge flow
- Other XML formats fall back to generic field extraction where needed
- PDF detection only validates Base64 payloads that decode cleanly and begin with a valid PDF header


## Separate PDF extraction

When validated Base64 PDF attachments are detected, the converter also extracts each embedded PDF as a separate `.pdf` download during output generation.

- validates Base64-encoded PDF attachments, exports a well-formed XML attachment manifest, and extracts each embedded PDF as a separate downloaded .pdf file.

- Attachment preview now prefers validated embedded PDF payloads over short numeric codes such as `1234`.
