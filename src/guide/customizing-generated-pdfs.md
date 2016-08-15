---
title: Customizing Generated PDFs
type: guide
order: 4
---

## Instance-Specific Parameters

You can adjust attributes of generated PDFs by providing custom settings for the generating method:

### orientation

The paper orientation of the PDF: `'portrait'` or `'landscape'`

Default: `'portrait'`

### size

The paper size of the PDF: `'letter'`, `'legal'`, `'a5'`, or any of [DOMPDF's built-in sizes](/guide/paper-sizes.html)

Default: `'letter'`
		
### filename

The name for the generated file (without the _.pdf_ extension). Accepts a string.

Default: `'Printmaker'`

### encrypt

Whether the PDF should be encrypted/password-protected. Accepts a boolean.

Default: `false`

### userPass

The user password. Accepts a string.

### ownerPass

The owner password. Accepts a string.

### canPrint

Whether the PDF can be printed without being unlocked. Accepts a boolean.

Default: `true`

### canModify

Whether the PDF can be modified without being unlocked. Accepts a boolean.

Default: `true`

### canCopy

Whether the PDF can be copied without being unlocked. Accepts a boolean.

Default: `true`

### canAdd

Whether the PDF allows adding comments or pages without being unlocked. Accepts a boolean.

Default: `true`

## Config Settings

In addition to these instance-specific settings, you can also override any of the default **[Config Settings](/guide/configuration.html)** for each individual PDF you generate.
