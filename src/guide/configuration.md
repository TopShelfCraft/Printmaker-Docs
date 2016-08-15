---
title: Configuration
type: guide
order: 6
---


## Adding a Custom Config

Custom config settings should be placed in your **craft/config/printmaker.php** file.

For example, if you want to set the default paper size and orientation, your `printmaker.php` file might look like this:

```php
<?php
return array(
    'defaultPaperSize' => 'a4',
    'defaultOrientation' => 'landscape',
);
```

You can return a single array of custom settings (as in the example above), or you can use Craft's [Multi-Environment Config](https://craftcms.com/docs/multi-environment-configs) setup to make your custom settings dynamic on a per-environment basis.

If you don't need to override a particular setting, you can leave it out of your config file, or set its value to `null`.


## Config Variables

Here is the definitive list of config settings you can add, and their default values:

```php
/**
 * Printmaker Config
 * @see http://topshelfcraft.com/printmaker/configuration
 */
 
return array(
 
	// Printmaker settings
 
	'defaultOrientation' => 'portrait',
	'compress' => false,
	'filename' => 'Printmaker',
	'extension' => 'pdf',
	'cachePath' => null,
	'cacheUrl' => null,
	'cacheDirectory' => 'Printmaker',
	'encrypt' => false,
	'userPass' => '',
	'ownerPass' => '',
	'canPrint' => true,
	'canModify' => true,
	'canCopy' => true,
	'canAdd' => true,
	'devMode' => false,
 
	// DOMPDF system settings
 
	'tempDir' => null,
	'fontDir' => null,
	'fontCache' => null,
	'logOutputFile' => null,
 
	// DOMPDF rendering defaults
 
	'defaultMediaType' => 'screen',
	'defaultPaperSize' => 'letter',
	'defaultFont' => 'serif',
	'dpi' => 96,
	'fontHeightRatio' => 1.1,
 
	// DOMPDF parsing defaults
 
	'isPhpEnabled' => false,
	'isRemoteEnabled' => true,
	'isJavascriptEnabled' => null,
	'isHtml5ParserEnabled' => null,
	'isFontSubsettingEnabled' => null,
 
	// DOMPDF debugging defaults
 
	'debugPng' => null,
	'debugKeepTemp' => null,
	'debugCss' => null,
	'debugLayout' => null,
	'debugLayoutLines' => null,
	'debugLayoutBlocks' => null,
	'debugLayoutInline' => null,
	'debugLayoutPaddingBox' => null,
 
);
```


### defaultPaperSize

The default page size: `'letter'`, `'legal'`, `'a4'`, or any of DOMPDF's other [built-in sizes](/guide/paper-sizes.html).

Default: `'letter'`

### defaultOrientation

The default page orientation.

`'portrait'` or `'landscape'`

### compress

Whether to compress the PDF output. Accepts a boolean.

Default: `false`

### filename

The default filename, sans _.pdf_ extension.

### extension

The default extension for files saved to disk (i.e. using the `url` or `email` output methods).

_Streamed files (i.e. using the `output` or `download` output methods) will always carry a _.pdf_ extension.

Default: `'pdf'`

### cacheDirectory

The path, relative to the document root, where printmaker Printmaker should cache saved PDFs.

For example, if your document root is, `/user/mysite.com/public` and you specify `'cache/pdfs'` as the **cacheDirectory**, your PDFs will be stored in `/user/mysite.com/public/cache/pdfs`.

Default: `'Printmaker'`

### cacheUrl & cachePath

The absolute path and fully qualified URL to the directory where you want Printmaker to store saved PDFs. (These parameters take precedence over the **cacheDirectory** parameter and would come in handy if you have a special setup where you need to specify the absolute path and URL instead of using PHP's implicit document root.)

For example, if your document root is, `/user/mysite.com/public`, you could specify `'/user/mysite.com/public/cache/pdfs'` as the **cachePath** and `http://mysite.com/cache/pdfs` as the **cacheUrl**.

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

### devMode

Whether Printmaker should allow DOMPDF to throw Exceptions if something goes wrong during PDF generation. This setting is similar to Craft's own `devMode` config setting, and will be automatically set to `true` if Craft is running in Dev Mode.

(This setting allows you to run Printmaker specifically in 'Dev Mode' even if Craft itself is _not_ running in Dev Mode.)

### tempDir

The location of DOMPDF's temporary directory.

The directory specified must be writeable by the webserver process. The temporary directory is required to download remote images and when using the PFDLib back-end.

### fontDir

The location of the directory where DOMPDF will store fonts and font metrics.

This directory must exist and be writable by the web server process.

### fontCache

The location of the DOMPDF font cache directory

This directory contains the cached font metrics for the fonts used by DOMPDF. This directory can be the same as `fontDir`

This directory must exist and be writable by the webserver process.

### logOutputFile

The log file DOMPDF will use to log its debugging events.

### defaultMediaType

The HTML target media view which should be rendered into PDF.

These standard HTML Media Descriptors (http://www.w3.org/TR/REC-html40/types.html) are available:

`'screen'`, `'tty'`, `'tv'`, `'projection'`, `'handheld'`, `'print'`, `'braille'`, `'aural'`, `'all'`

_Note: `aural` is deprecated in CSS 2.1 because it is replaced by `speech` in CSS 3._

Even though the generated PDF file is intended for print output, the target stylesheets and content might be different (e.g. `screen` or `projection`).

Default: `'screen'`

### defaultFont

Default: `'serif'`

### dpi

This setting determines the default DPI setting for images and fonts.

The DPI may be overridden for inline images by explictly setting the image's width & height style attributes. For example, if an image's native width is 600 pixels and you specify the image's width as 72 points, the image will have a DPI of 600 in the rendered PDF.

The DPI of background images can not be overridden and is controlled entirely via this parameter.

For the purposes of DOMPDF, pixels per inch (PPI) = dots per inch (DPI).

If a size in html is given as px (or without unit as image size), this determines the corresponding size in pt at 72 DPI. (This adjusts the relative sizes to be similar to the rendering of the HTML page in a reference browser.

In PDF, 1 pt = 1/72 inch.

### fontHeightRatio

A ratio applied to the fonts' height to normalize them to a reference browser's line height.

Default: `1.1`

### isPhpEnabled

If this setting is set to true then DOMPDF will automatically evaluate embedded PHP contained within `<script type="text/php"> ... </script>` tags.

<p class="tip">**Enabling `isPhpEnabled` for documents you do not trust (e.g. arbitrary remote HTML pages) is a security risk. Embedded scripts are run with the same level of system access available to Printmaker. Leave this option set to `false` if you intend to process untrusted documents.**</p>

Default: `false`

### isRemoteEnabled

If this setting is set to true, DOMPDF will access remote sites for images and CSS files as required.

<p class="tip">This can be a security risk, particularly in combination with `isPhpEnabled`, as this could allow anonymous users to download dubious internet content using your server as a proxy, and it could allow malicious PHP code in remote pages to be executed by your server with your account privileges.</p>

This setting is enabled by default because Craft generates fully qualified URLs for Assets, so the vast majority of customers need to support remote content, even when that "remote content" is being served from their own servers. Additionally, this allows Printmaker to use content from remote Asset Sources like Amazon S3, as well as content served by CDN.

**If you're able to, it's best to disable this setting to help lock down your server.**

Default: `true`

### isJavascriptEnabled

If this setting is set to true then DOMPDF will automatically insert JavaScript code contained within `<script type="text/javascript"> ... </script>` tags.

### isHtml5ParserEnabled

DOMPDF includes the experimental HTML5 Lib parser. The HTML5 parser is not as mature as the default parser, but may be more tolerant of poorly-formed HTML.

Default: `false`

### isFontSubsettingEnabled

Whether to enable font subsetting in DOMPDF.

Default: `false`

### debugX

The `debugX` parameters adjust DOMPDF's internal debugging behavior. It isn't likely that you'll need to change these, but they're exposed just in case you really know what you're doing and want to mess with stuff.

(c.f. https://github.com/dompdf/dompdf/blob/master/src/Options.php)
