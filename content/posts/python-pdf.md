---
title: "Python Pdf"
date: 2021-08-20T13:28:58-07:00
---

# Goal: extract text and refs from pdfs

I want to extact text and references from pdfs of scientific papers.

In an ideal world, this would include an OCR ability for older papers, but for now, let's just consider modern ones that are already text.

## What's out there?

[grobid](https://github.com/kermitt2/grobid)

*in dev* [sciencebeam](https://github.com/elifesciences/sciencebeam)

*unmaintained* [allenai: science parse v1](https://github.com/allenai/science-parse)

*abandoned* [allenai: science parse v2](https://github.com/allenai/spv2) 

[pdfminer](https://github.com/euske/pdfminer/)

[pdfextract](https://github.com/CrossRef/pdfextract)


Extraction benchmarks:
https://github.com/ckorzen/pdf-text-extraction-benchmark


## Plan

Briefly, it seems that grobid is the most mature, maintained, and feature-rich solution.  Running it is a bit of an ordeal.  Am currently attempting to do so via the docker image, but with the complication that the image is built for amd64 and I am now on M1.
