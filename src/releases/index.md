---
title: Changelog
type: releases
order: 0
---

### 1.3.2

- Updated DOMPDF library files, resolving compatibility issues with PHP 7.2.

### 1.3.1

- Updated DOMPDF library files.

### 1.3.0

- Added Twig extension to provide a `printmaker` global variable as a shortcut to `craft.printmaker`.
- Updated DOMPDF library files.

### 1.2.0

- Updated DOMPDF library files.

### 1.1.0

- Updated DOMPDF library files.
- Updated docs with code examples for the `email()` method.

### 1.0.3

- Updated DOMPDF library files

### 1.0.2

- Added plugin icon.

### 1.0.1

- Upgraded DOMPDF library to 0.7, which adds PHP namespace support, object-based Options config, initial support for SVG, updated fonts, optimized performance, Unicode support, better float support, and more.
- DOMPDF dropped support for PHP 5.3, so **Printmaker now requires PHP 5.4+**
- Added the ability to set config options via a handy `config/printmaker.php` settings file.
- Enabled remote images by default, because basically everybody uses them.
- Added the `PdfModel->email()` method for sending generated PDFs as email attachments.
- Added Craft 2.5 goodies, like a nice juicy updates feed. **Printmaker now requires Craft 2.5+**
- Printmaker has officially graduated beta!

### 0.10.0

- Updated for CraftCMS 2.5+ compatibility

### 0.9.3

- Fixed a bug where failing to provide a settings array could spawn a template error.

### 0.9.1

- **First beta release!**
- Added: `printmaker.pdfFromTemplate`
- Added: `printmaker.pdfFromHtml`
