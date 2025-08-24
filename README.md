# Quarto IMS Basic Template Extension

A professional Quarto extension that provides a clean, academic-style PDF template optimized for research documents and reports. This extension uses the KOMA-Script `scrartcl` document class with carefully configured typography and layout.

## Features

- **Clean Academic Design**: Professional typography using Charter math fonts and Source Sans Pro
- **Flexible Layout**: A4 paper size with optimized margins for readability
- **Rich Content Support**: 
  - Python code execution with matplotlib integration
  - Mermaid.js flowchart rendering
  - Mathematical equations with proper numbering
  - Cross-referencing for figures, tables, and equations
  - Bibliography support with APA style
- **Modern Typography**: Sans serif fonts with proper spacing and microtype enhancements
- **Custom Headers/Footers**: Integrated branding with IMS logo assets

## Installing

Install this extension template directly from this repository:

```bash
quarto use template fpontejos/quarto-ims-basic
```

This will install the extension and create a template document (`template.qmd`) that demonstrates all available features.

Alternatively, to add this extension to an existing project:

```bash
quarto add /path/to/demo-extension/_extensions/quarto-ims-basic
```

## Using

Once installed, specify the format in your document's YAML front matter:

```yaml
---
title: "Your Document Title"
subtitle: "Optional Subtitle"
format:
  quarto-ims-pdf:
    keep-tex: true  
author:
  - name: "Your Name"
bibliography: references.bib
semester: "Fall Semester 2025-2026"
version: "v1.0.0"
---
```

## Format Options

The `quarto-ims-pdf` format supports standard Quarto PDF options plus:

### Document Metadata
- `semester`: Display semester information in headers/footers
- `version`: Document version number
- `subtitle`: Optional document subtitle

### Built-in Features
- **Document Class**: Uses `scrartcl` (KOMA-Script article)
- **Paper Size**: A4 with optimized margins
- **Font**: 11pt base size with Charter math and Source Sans Pro
- **PDF Engine**: LuaLaTeX for better font support
- **Bibliography**: APA style with biblatex
- **Cross-references**: Automatic numbering for figures, tables, equations

## Template Structure

```
_extensions/quarto-ims/
├── _extension.yml          # Extension configuration
├── assets/                 # Logo and branding assets
│   ├── IMS2Col.png
│   ├── IMS_Circle_*.png
│   └── ...
├── partials/              # LaTeX template partials
│   ├── before-title.tex   # Preamble and packages
│   ├── before-body.tex    # Header/footer setup
│   └── title.tex          # Title page formatting
└── styles.css             # HTML output styles (placeholder)
```

## Example Content

The template demonstrates:

1. **Python Integration**: Matplotlib plots with subfigures
2. **Mermaid Diagrams**: Flowcharts and process diagrams  
3. **Mathematical Notation**: Equations with cross-references
4. **Tables and Figures**: Professional formatting with captions
5. **Bibliography**: Academic citations using BibTeX
6. **Page Controls**: Manual page breaks and formatting

See `template.qmd` for a complete working example.

## Requirements

- Quarto >= 1.6.0
- LaTeX distribution with LuaLaTeX
- Python (optional, for code execution)

## Customization

### Fonts
The template uses Charter for math and Source Sans Pro for text. Modify `partials/before-title.tex` to change fonts:

```latex
\usepackage[charter]{mathdesign}
\usepackage{sourcesanspro}
```

### Layout
Adjust margins and spacing in `partials/before-title.tex`:

```latex
\usepackage[a4paper,
    left=2.0cm, right=2.0cm, 
    top=3cm, bottom=3cm]{geometry}
```

