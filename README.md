php-pdftoppm
=============
[![Build Status](https://scrutinizer-ci.com/g/waarneembemiddeling/php-pdftoppm/badges/build.png?b=master)](https://scrutinizer-ci.com/g/waarneembemiddeling/php-pdftoppm/build-status/master)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/waarneembemiddeling/php-pdftoppm/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/waarneembemiddeling/php-pdftoppm/?branch=master)

PHP wrapper for the [pdftoppm command][1] which is part of
[poppler-utils][2].

The Pdftoppm is a library that handles conversion of PDF files to images. It is available on variety of systems.

Available packages:
[http://pkgs.org/download/poppler-utils][3]

Usage
-------------
```php
use Wb\PdfToPpm\PdfToPpm;
$pdfToPpm = PdfToPpm::create();
// $result is an instance of \FilesystemIterator
$result1 = $pdfToPpm->convertPdf('path/to/pdf');
$result2 = $pdfToPpm->convertPdf('path/to/pdf', 'path/to/other/destination/dir/then/tmp');

// Save as png
$result3 = $pdfToPpm->convertPdf('path/to/pdf', 'path/to/other/destination/dir/then/tmp', true);

// Set specific resolution
$result4 = $pdfToPpm->convertPdf('path/to/pdf', 'path/to/other/destination/dir/then/tmp', true, 300);

// Set filename (skips generating random directory),
// 'ExampleFileName' will return 'ExampleFileName-1.png', 'ExampleFileName-2.png' files.
$filename = 'ExampleFileName';
$result5 = $pdfToPpm->convertPdf('path/to/pdf', 'path/to/other/destination/dir/then/tmp', true, 300, $filename);


```

Testing
-------------

```
cp phpunit.xml.dist phpunit.xml
```

Change the phpunit.xml ```env``` ```binary``` directive if necessary.

```
composer install
```

```
php vendor/bin/phpunit
```

[1]: http://linux.die.net/man/1/pdftoppm
[2]: http://en.wikipedia.org/wiki/Poppler_(software)
[3]: http://pkgs.org/download/poppler-utils
