---
layout: post
title: PDF to E-book Conversion for Kindle (Handling math or Farsi)
comments: True
---

Short answer: Either `.pdf > Calibre > .azw3` or `.pdf > K2pdfopt 
> .pdf > Calibre > .azw3`. The command for `K2pdfopt` is `k2pdfopt f.pdf f_pdfopt.pdf`. The command line version of `Calibre` is `ebook-convert f.pdf f.azw3`.

What to expect:

- `K2pdfopt` alone doesn't produce a sharp output. The output is PDF, which is not the best option for e-book readers.
- `Calibre > .azw3` alone for Farsi, gives the closest result to the same formatting of the book. This means that if the original aspect ratio was too different from the e-book reader's aspect ratio, a margin will appear. Also, the font would probably be too small. For academic papers that use math symbols, the math doesn't appear when viewed on the reader. That's probably because it is left to the reader to handle it.
- `K2pdfopt > Calibre > .mobi`, for some reason any `.mobi` file I produced had an extra right margin on my kindle and I couldn't get rid of it with any negative margin or other parameters.
- `K2pdfopt > Calibre > .azw3`, has a small bottom margin which again couldn't be removed but it was fine to have.

For more details refer to:

- [Arabic/Persian text on Kindle 3](http://www.mobileread.com/forums/showthread.php?s=8d681036217c3e68da2614f2a849eb2c&t=195726&page=2)
- [How To Convert A PDF File For Better Kindle Or Smartphone Viewing](http://techlogon.com/2012/01/04/how-to-convert-a-pdf-file-for-better-kindle-or-smartphone-viewing/)
- [How to Convert PDF Files for Easy Ebook Reading](http://www.howtogeek.com/69481/how-to-convert-pdf-files-for-easy-ebook-reading/)
