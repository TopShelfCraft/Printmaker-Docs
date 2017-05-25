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

```twig
{{ pdf.output }}
```


### `PdfModel.download`

Streams the PDF as a download/attachment to the browser.

_(Streaming file contents to the client won't work if other page content has already been sent. Therefore, you should invoke this method before/above any other content is output to the template.)_

```twig
{{ pdf.output }}
```


### `PdfModel.url`

Returns the URL of the generated PDF file.

```twig
{% set pdfUrl = printmaker.pdfFromTemplate('_myTemplate', someVars, someSettings).url %}

<a href="{{ pdfUrl }}">
   Download your PDF!
</a>
```


## Email the PDF

### `PdfModel.email`

Sends an email with the generated PDF attached.

* **filename** Overrides the name of the file as it is attached to the email
* **settings** Attributes to set on the EmailModel before it gets sent
* **variables** The variables that will be available to to the email template (in addition to `fileUrl`)

```twig
{% set variables = {
   userName : currentUser.friendlyName
} %}
 
{% set settings = {
   toEmail: 'someone@website.com',
   subject: "Here's your PDF!",
   body: "Hi {{ userName }}! Your PDF is attached."
} %}
 
{% set pdf = printmaker.pdfFromTemplate('_pdf/_myTemplate', someVars, someSettings) %}
 
{% do pdf.email('YourPDF.pdf', settings, variables %} 
```
