<!-- -*- coding: utf-8 -*- -->
# A tool to fix ToUnicod CMap in PDF to prevent extracted text from being garbled

[ English / [日本語 (Japanese)](Readme.ja.md) ]

When copying and pasting text from a PDF file, depending on the PDF, kanji characters such as "見" and "高" are often garbled into similar but different characters (e.g. special characters such as Kangxi Radical and CJK Radicals Supplement).
This tool fixes such PDF that raises the garbled text extraction and generates a PDF that does not raise the garbled.

## Caution

It is not possible to reverse the conversion from the PDF generated by this tool to the original PDF (it is irreversible).
It is also possible that the generated PDF may be corrupted without you noticing it.
Be sure to keep a backup of the original PDF.

## Usage

```
$ pdf-fix-tuc
Fix ToUnicode CMap in PDF 0.0.0
Copyright (C) 2021 Masamichi Hosoda. All rights reserved.
License: BSD-2-Clause

https://github.com/trueroad/pdf-fix-tuc

Usage: pdf-fix-tuc [options] [INPUT.pdf OUTPUT.pdf] ...

  -h, --help
    Print help and exit
  -V, --version
    Print version and exit
  --verbose
    Verbose

Output PDF settings (QPDF):
  --linearize
    Output linearized (web-optimized) PDF
  --object-streams=[preserve|disable|generate]   (default=preserve)
    Settings for object streams
  --newline-before-endstream
    Output newline before endstream
  --qdf
    Output QDF

$
```

## Install

### Required

* C++11 compiler (g++ 4.9+ etc.)
* libqpdf
* pkg-config etc.
* Autoconf 2.69+
* Automake

When you would like to use packages for preparing the required library, the following might be convenient.

* Debian / Ubuntu
    + libqpdf-dev
* Fedora
    + qpdf-devel
* Cygwin
    + libqpdf-devel

### Build & install

```
$ git clone https://github.com/trueroad/pdf-fix-tuc.git
$ cd pdf-fix-tuc
$ ./autogen.sh
$ mkdir build
$ cd build
$ ../configure
$ make
$ make install
```

## License

Copyright (C) 2021 Masamichi Hosoda. All rights reserved.

License: BSD-2-Clause

See [LICENSE](./LICENSE).
