---
title: Templating Overview
type: guide
order: 2
---

### Basic Usage

Printmaker loads or generates a PDF using the source(s) and settings you provide.

```twig
{% set html = "<html>Howdy, world!</html>" %}
{% set settings = { orientation : 'portrait' } %}
{% set pdfUrl = craft.printmaker.pdfFromHtml(html, settings).url %}
 
{{ pdfUrl }}
```

All of Printmaker's [PDF-generating methods](/guide/generating-a-pdf.html) will return a *[PdfModel](/guide/working-with-pdfs.html)* object, which allows you to edit, output, download, save, or send the generated PDF via your template.
