# DubliNet XML Converter

A GitHub-ready single-file HTML tool for converting DubliNet XML into **template-selectable DOCX or HTML outputs**.

## What is included

- Official DubliNet code tables embedded from the uploaded workbook
- Safer nationality, legal-base, member-state, ISO and ICAO interpretation
- Template chooser covering the uploaded take charge, take back, transfer, relocation, exchange-of-information and reply layouts
- DOCX export and browser-ready HTML export
- DubliNet-style preview with header, breadcrumb, progress rail, section cards and field rows inspired by the uploaded templates

## Output templates included

- Take charge / take back request and reply variants
- Re-examination templates
- Transfer confirmation, supervised / escorted / voluntary transfer templates
- Relocation templates
- Exchange-of-information and information-reply templates
- General-case-data / section-specific templates for TC and TB notifications

## Notes

The strongest semantic mapping is still the dedicated `TakeChargeRequestForm` flow. For other XML structures, the converter falls back to a generic DubliNet-style renderer that keeps all detected XML leaf fields visible while still using the selected template shell.
