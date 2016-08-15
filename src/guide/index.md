---
title: Introduction
type: guide
order: 0
---

Printmaker is a template-based PDF toolkit. You can use Printmaker to easily create, concatenate, and output PDF files from your Craft CMS templates.

For example, you can output a PDF from any template in just one line of code, like this:

```twig
{{ craft.printmaker.pdfFromTemplate('docs/_pdf').output }}
```

### Features

- Five output modes:

 - **output** direction to the browser
 - **download** the file
 - cache the file and output its **URL**
 - **email** the file as an attachment

- Handles most CSS 2.1 (and a few CSS3) properties, including floats, `@import`, `@media` & `@page` rules

- Supports most presentational HTML 4.0 attributes

- Supports external stylesheets, either local or through http/ftp (via fopen-wrappers)

- Supports complex tables, including row & column spans, separate & collapsed border models, individual cell styling image support (GIF, PNG, BMP & JPEG)


### Requirements

- [Craft CMS](https://craftcms.com/) 2.5+
- [PHP](http://php.net/downloads.php) 5.4+


### DOMPDF Limitations & Known Issues

Printmaker uses the _DOMPDF_ library to generate PDF files. This library carries some known limitations, which you should be aware of before beginning your project:

- The parser is not particularly tolerant to poorly-formed HTML input. (Using Tidy first may help.)
- Large files or large tables can take a while to render.
- While CSS floats are supported, complex floats may run into layout glitches every once in a blue moon.


### Buy Printmaker

Printmaker is available from these popular Craft plugin marketplaces:


<a class="button" href="https://craftpl.us/plugins/printmaker">CraftPlus</a><span class="light info">$49</span>

<a class="button" href="https://straightupcraft.com/craft-plugins/printmaker">Straight Up Craft</a><span class="light info">$49</span>
