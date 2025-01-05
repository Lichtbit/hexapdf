## Simple Text Rendering Benchmark

The Python PDF generation library ReportLab contains a demo/benchmarking application that takes the
Project Gutenberg text of Homer's Odyssey (contains about 12.000 lines and about 700.000 characters)
and creates a PDF version from it. This benchmark is derived from that demo.

No advanced text features are used or needed by this benchmark, only the raw text output performance
is tested.


## Benchmark Setup

The text of the Odyssey is written onto A4 pages with a margin of 72 points, showing each line of
the source text using the most basic text drawing methods available, without line wrapping or text
measuring.

To see how the amount of text influences the performance, the benchmark is done by concatenating the
text multiple times (1x, 5x and 10x by default). Additionally, all multiplication factors are
combined once with the standard PDF Type1 font Times-Roman and once with a TrueType font (DejaVu
Sans by default).

Each benchmark script (except the jPDFWriter and pdfkit ones) can be invoked standalone in the
following way: `script-executable TXT_FILE OUTPUT_FILE [TTF_FILE]`.

The list of the benchmarked libraries:

**HexaPDF**

: Homepage: <http://hexapdf.gettalong.org>\\
  Language: Ruby\\
  Version: Latest version

**Prawn**

: Homepage: <https://prawnpdf.org>\\
  Language: Ruby\\
  Version: 2.5.0

**ReportLab**

: Homepage: <https://www.reportlab.com/opensource/>\\
  Language: Python\\
  Version: 4.2.2 + accel extension

  ReportLab has a module that implements some features in C to speed up the execution. This module
  is used in the benchmark.

**fpdf2**

: Homepage: <https://pyfpdf.github.io/fpdf2/>\\
  Language: Python\\
  Version: 2.7.9

**jPDFWriter**

: Homepage: <https://www.qoppa.com/pdfwriter/>\\
  Language: Java\\
  Version: v2016R1

  Qoppa Software provides the free jPDFWriter library which is needed for benchmarking this library.
  The Java source code file for the benchmark needs to be compiled and the jPDFWriter-JAR put onto
  the `CLASSPATH` environment variable.

  Note that TrueType fonts don't seem to be supported.

**TCPDF**

: Homepage: <https://tcpdf.org/>\\
  Language: PHP\\
  Version: 6.7.5

**PDF::API2**

: Homepage: <http://search.cpan.org/perldoc/PDF::API2>\\
  Language: Perl\\
  Version: 2.047

**PDFKit**

: Homepage: <https://pdfkit.org/>\\
  Language: Javascript\\
  Version: 1.0.0
