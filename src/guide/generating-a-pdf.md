---
title: Generating a PDF
type: guide
order: 3
---

### Basic Usage

Printmaker provides methods to create a new PDF file from HTML or template source.

These methods will return a *[PdfModel](/guide/working-with-pdfs.html)* object, which allows you to edit, output, download, save, or send the generated PDF via your template.

You can supply HTML code directly using the `pdfFromHtml` method, or generate a PDF from a compiled template using the `pdfFromTemplate` method.


### `printmaker.pdfFromHtml`

The `pdfFromHtml()` method accepts two parameters:

* **html** _(required)_ &mdash; the HTML which will be used to generate the PDF
* **settings** _(optional)_ &mdash; any [custom settings](/guide/customizing-generated-pdfs.html#Instance-Specific-Parameters) for the PDF engine

```twig
{% set html %}
  <html>Howdy, world!</html>
{% endset %}
{% set settings = { orientation : 'portrait' } %}
 
{% set pdf = craft.printmaker.pdfFromHtml(html, settings) %}
```

### `printmaker.pdfFromTemplate`

The `pdfFromTemplate()` method accepts three parameters:

- a **template** _(required)_ &mdash; the path/name of the Twig template, just like you'd use in an `{% raw %}{% include %}{% endraw %}` tag
- **variables** _(optional)_ &mdash; an object containing any variables you want to pass to the template for use in rendering its content
- **settings** _(optional)_ &mdash; any [custom settings](/guide/customizing-generated-pdfs.html#Instance-Specific-Parameters) for the PDF engine

```twig
{% set vars = { title: 'Howdy, world!', foo: entry.fooField } %}
{% set settings = { orientation : 'portrait' } %}
 
{% set pdfUrl = printmaker.pdfFromTemplate('_pdf/_myTemplate', vars, settings) %}
```
