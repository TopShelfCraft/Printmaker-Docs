---
title: Working with PDFs
type: guide
order: 5
---

## The `PdfModel`

Whenever you’re dealing with a Printmaker-generated PDF, you’re actually working with a _PdfModel_ object.



## Output the PDF

These methods save the PDF to disk so that you can output it to the client.

### `PdfModel.output`

Outputs the PDF directly to the browser, as if the current URL pointed directly to your generated PDF file.

_(Streaming file contents to the client won't work if other page content has already been sent. Therefore, you should invoke this method before/above any other content is output to the template.)_

### `PdfModel.download`

Streams the PDF as a download/attachment to the browser.

_(Streaming file contents to the client won't work if other page content has already been sent. Therefore, you should invoke this method before/above any other content is output to the template.)_

### `PdfModel.url`

Returns the URL of the generated PDF file.


## Email the PDF

### `PdfModel.email`

// TODO
