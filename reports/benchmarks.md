# Benchmark Report

> Generated on 2026-09-07 at 11:38:05 UTC
>
> System: linux | AMD EPYC 7763 64-Core Processor (4 cores) | 16GB RAM | Bun 1.4.2
>
> Libraries: @libpdf/core 0.4.2 (this repo), pdf-lib 1.17.1, @cantoo/pdf-lib 2.9.1

---

## Contents

- [Comparison](#comparison)
- [Copying](#copying)
- [Drawing](#drawing)
- [Forms](#forms)
- [Loading](#loading)
- [Saving](#saving)
- [Splitting](#splitting)

## Comparison

### Load PDF

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| libpdf          |    51.4 |  19.47ms |  28.40ms | ±4.23% |      26 |
| @cantoo/pdf-lib |     4.5 | 221.04ms | 231.50ms | ±1.42% |      10 |
| pdf-lib         |     4.5 | 223.64ms | 230.05ms | ±1.30% |      10 |

- **libpdf** is 11.35x faster than @cantoo/pdf-lib
- **libpdf** is 11.49x faster than pdf-lib

### Create blank PDF

| Benchmark       | ops/sec |  Mean |    p99 |    RME | Samples |
| :-------------- | ------: | ----: | -----: | -----: | ------: |
| libpdf          |   10.6K |  95us |  237us | ±4.16% |   5,290 |
| pdf-lib         |    2.8K | 363us | 1.46ms | ±2.64% |   1,378 |
| @cantoo/pdf-lib |    2.5K | 393us | 1.72ms | ±2.90% |   1,272 |

- **libpdf** is 3.84x faster than pdf-lib
- **libpdf** is 4.16x faster than @cantoo/pdf-lib

### Add 10 pages

| Benchmark       | ops/sec |  Mean |    p99 |    RME | Samples |
| :-------------- | ------: | ----: | -----: | -----: | ------: |
| libpdf          |    7.9K | 127us |  232us | ±1.34% |   3,927 |
| @cantoo/pdf-lib |    2.2K | 448us | 2.44ms | ±4.73% |   1,116 |
| pdf-lib         |    2.2K | 455us | 1.98ms | ±4.45% |   1,099 |

- **libpdf** is 3.52x faster than @cantoo/pdf-lib
- **libpdf** is 3.57x faster than pdf-lib

### Draw 50 rectangles

| Benchmark       | ops/sec |   Mean |    p99 |    RME | Samples |
| :-------------- | ------: | -----: | -----: | -----: | ------: |
| libpdf          |    2.7K |  370us |  950us | ±1.53% |   1,352 |
| pdf-lib         |   617.9 | 1.62ms | 6.89ms | ±9.25% |     309 |
| @cantoo/pdf-lib |   540.6 | 1.85ms | 7.07ms | ±8.25% |     271 |

- **libpdf** is 4.37x faster than pdf-lib
- **libpdf** is 5.00x faster than @cantoo/pdf-lib

### Load and save PDF

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| libpdf          |    52.8 |  18.94ms |  27.40ms | ±3.92% |      27 |
| pdf-lib         |     3.1 | 320.54ms | 335.91ms | ±1.46% |      10 |
| @cantoo/pdf-lib |     1.9 | 539.74ms | 573.06ms | ±1.73% |      10 |

- **libpdf** is 16.92x faster than pdf-lib
- **libpdf** is 28.49x faster than @cantoo/pdf-lib

### Load, modify, and save PDF

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| pdf-lib         |     3.2 | 314.98ms | 326.20ms | ±1.31% |      10 |
| libpdf          |     2.8 | 354.86ms | 371.18ms | ±1.46% |      10 |
| @cantoo/pdf-lib |     1.8 | 550.60ms | 627.03ms | ±4.19% |      10 |

- **pdf-lib** is 1.13x faster than libpdf
- **pdf-lib** is 1.75x faster than @cantoo/pdf-lib

### Extract single page from 100-page PDF

| Benchmark       | ops/sec |   Mean |     p99 |    RME | Samples |
| :-------------- | ------: | -----: | ------: | -----: | ------: |
| libpdf          |   269.1 | 3.72ms |  4.62ms | ±1.09% |     135 |
| pdf-lib         |   109.5 | 9.13ms | 11.60ms | ±2.12% |      55 |
| @cantoo/pdf-lib |   103.1 | 9.70ms | 15.18ms | ±3.13% |      52 |

- **libpdf** is 2.46x faster than pdf-lib
- **libpdf** is 2.61x faster than @cantoo/pdf-lib

### Split 100-page PDF into single-page PDFs

| Benchmark       | ops/sec |    Mean |      p99 |     RME | Samples |
| :-------------- | ------: | ------: | -------: | ------: | ------: |
| libpdf          |    23.6 | 42.40ms |  46.45ms |  ±2.93% |      12 |
| pdf-lib         |    13.8 | 72.66ms |  78.71ms |  ±4.21% |       7 |
| @cantoo/pdf-lib |    11.7 | 85.44ms | 100.85ms | ±10.43% |       6 |

- **libpdf** is 1.71x faster than pdf-lib
- **libpdf** is 2.02x faster than @cantoo/pdf-lib

### Split 2000-page PDF into single-page PDFs (0.9MB)

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| libpdf          |     1.3 | 776.11ms | 776.11ms | ±0.00% |       1 |
| pdf-lib         |   0.722 |    1.39s |    1.39s | ±0.00% |       1 |
| @cantoo/pdf-lib |   0.671 |    1.49s |    1.49s | ±0.00% |       1 |

- **libpdf** is 1.79x faster than pdf-lib
- **libpdf** is 1.92x faster than @cantoo/pdf-lib

### Copy 10 pages between documents

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |   211.1 |  4.74ms |  5.54ms | ±1.18% |     106 |
| pdf-lib         |    86.9 | 11.51ms | 12.65ms | ±1.20% |      44 |
| @cantoo/pdf-lib |    75.7 | 13.20ms | 14.53ms | ±1.52% |      38 |

- **libpdf** is 2.43x faster than pdf-lib
- **libpdf** is 2.79x faster than @cantoo/pdf-lib

### Merge 2 x 100-page PDFs

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    61.6 | 16.24ms | 19.77ms | ±1.93% |      31 |
| pdf-lib         |    18.9 | 52.91ms | 54.22ms | ±0.71% |      10 |
| @cantoo/pdf-lib |    15.7 | 63.69ms | 64.55ms | ±0.77% |       8 |

- **libpdf** is 3.26x faster than pdf-lib
- **libpdf** is 3.92x faster than @cantoo/pdf-lib

### Fill FINTRAC form fields

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    44.3 | 22.59ms | 39.35ms | ±7.84% |      23 |
| pdf-lib         |    36.4 | 27.50ms | 37.79ms | ±4.77% |      19 |
| @cantoo/pdf-lib |    35.4 | 28.21ms | 41.89ms | ±6.48% |      18 |

- **libpdf** is 1.22x faster than pdf-lib
- **libpdf** is 1.25x faster than @cantoo/pdf-lib

### Fill and flatten FINTRAC form

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    54.4 | 18.40ms | 23.88ms | ±3.93% |      28 |
| pdf-lib         |  FAILED |       - |       - |      - |       0 |
| @cantoo/pdf-lib |    32.1 | 31.12ms | 51.32ms | ±8.80% |      17 |

- **libpdf** is 1.69x faster than @cantoo/pdf-lib

## Copying

### Copy pages between documents

| Benchmark                       | ops/sec |   Mean |     p99 |    RME | Samples |
| :------------------------------ | ------: | -----: | ------: | -----: | ------: |
| copy 1 page                     |   910.6 | 1.10ms |  2.19ms | ±2.58% |     456 |
| copy 10 pages from 100-page PDF |   216.2 | 4.62ms |  5.57ms | ±1.31% |     109 |
| copy all 100 pages              |   122.0 | 8.19ms | 11.57ms | ±2.16% |      62 |

- **copy 1 page** is 4.21x faster than copy 10 pages from 100-page PDF
- **copy 1 page** is 7.46x faster than copy all 100 pages

### Duplicate pages within same document

| Benchmark                                 | ops/sec |   Mean |    p99 |    RME | Samples |
| :---------------------------------------- | ------: | -----: | -----: | -----: | ------: |
| duplicate all pages (double the document) |   996.7 | 1.00ms | 1.43ms | ±0.68% |     499 |
| duplicate page 0                          |   986.0 | 1.01ms | 1.45ms | ±0.92% |     493 |

- **duplicate all pages (double the document)** is 1.01x faster than duplicate page 0

### Merge PDFs

| Benchmark               | ops/sec |    Mean |     p99 |    RME | Samples |
| :---------------------- | ------: | ------: | ------: | -----: | ------: |
| merge 2 small PDFs      |   639.2 |  1.56ms |  2.10ms | ±1.11% |     320 |
| merge 10 small PDFs     |   120.1 |  8.33ms | 13.75ms | ±2.84% |      61 |
| merge 2 x 100-page PDFs |    67.3 | 14.85ms | 16.38ms | ±1.18% |      34 |

- **merge 2 small PDFs** is 5.32x faster than merge 10 small PDFs
- **merge 2 small PDFs** is 9.49x faster than merge 2 x 100-page PDFs

## Drawing

| Benchmark                           | ops/sec |   Mean |    p99 |    RME | Samples |
| :---------------------------------- | ------: | -----: | -----: | -----: | ------: |
| draw 100 lines                      |    1.7K |  589us | 1.26ms | ±1.37% |     849 |
| draw 100 rectangles                 |    1.6K |  620us | 1.34ms | ±1.67% |     806 |
| draw 100 circles                    |    1.0K |  979us | 1.80ms | ±1.53% |     512 |
| create 10 pages with mixed content  |   650.8 | 1.54ms | 2.96ms | ±2.30% |     326 |
| draw 100 text lines (standard font) |   599.2 | 1.67ms | 3.00ms | ±1.77% |     300 |

- **draw 100 lines** is 1.05x faster than draw 100 rectangles
- **draw 100 lines** is 1.66x faster than draw 100 circles
- **draw 100 lines** is 2.61x faster than create 10 pages with mixed content
- **draw 100 lines** is 2.83x faster than draw 100 text lines (standard font)

## Forms

| Benchmark         | ops/sec |    Mean |     p99 |    RME | Samples |
| :---------------- | ------: | ------: | ------: | -----: | ------: |
| read field values |   343.7 |  2.91ms |  5.15ms | ±1.88% |     172 |
| get form fields   |   308.7 |  3.24ms |  5.49ms | ±2.92% |     155 |
| flatten form      |   119.9 |  8.34ms | 10.96ms | ±1.67% |      61 |
| fill text fields  |    75.3 | 13.28ms | 24.08ms | ±5.84% |      38 |

- **read field values** is 1.11x faster than get form fields
- **read field values** is 2.87x faster than flatten form
- **read field values** is 4.56x faster than fill text fields

## Loading

| Benchmark              | ops/sec |    Mean |     p99 |    RME | Samples |
| :--------------------- | ------: | ------: | ------: | -----: | ------: |
| load small PDF (888B)  |   16.0K |    63us |   194us | ±2.65% |   7,986 |
| load medium PDF (19KB) |   11.1K |    90us |   162us | ±0.66% |   5,530 |
| load form PDF (116KB)  |   768.3 |  1.30ms |  2.49ms | ±1.99% |     385 |
| load heavy PDF (2.0MB) |    55.2 | 18.11ms | 19.12ms | ±1.65% |      28 |

- **load small PDF (888B)** is 1.44x faster than load medium PDF (19KB)
- **load small PDF (888B)** is 20.79x faster than load form PDF (116KB)
- **load small PDF (888B)** is 289.16x faster than load heavy PDF (2.0MB)

## Saving

| Benchmark                          | ops/sec |    Mean |     p99 |    RME | Samples |
| :--------------------------------- | ------: | ------: | ------: | -----: | ------: |
| save unmodified (19KB)             |    8.8K |   114us |   317us | ±2.41% |   4,392 |
| incremental save (19KB)            |    6.0K |   166us |   342us | ±1.09% |   3,016 |
| save with modifications (19KB)     |    1.2K |   840us |  1.56ms | ±1.74% |     596 |
| save heavy PDF (2.0MB)             |    53.9 | 18.55ms | 19.88ms | ±1.10% |      27 |
| incremental save heavy PDF (2.0MB) |    49.4 | 20.24ms | 30.59ms | ±6.26% |      26 |

- **save unmodified (19KB)** is 1.46x faster than incremental save (19KB)
- **save unmodified (19KB)** is 7.37x faster than save with modifications (19KB)
- **save unmodified (19KB)** is 162.97x faster than save heavy PDF (2.0MB)
- **save unmodified (19KB)** is 177.76x faster than incremental save heavy PDF (2.0MB)

## Splitting

### Extract single page

| Benchmark                                | ops/sec |    Mean |     p99 |    RME | Samples |
| :--------------------------------------- | ------: | ------: | ------: | -----: | ------: |
| extractPages (1 page from small PDF)     |   867.9 |  1.15ms |  2.96ms | ±3.11% |     434 |
| extractPages (1 page from 100-page PDF)  |   270.5 |  3.70ms |  7.42ms | ±2.95% |     136 |
| extractPages (1 page from 2000-page PDF) |    17.4 | 57.48ms | 58.75ms | ±0.73% |      10 |

- **extractPages (1 page from small PDF)** is 3.21x faster than extractPages (1 page from 100-page PDF)
- **extractPages (1 page from small PDF)** is 49.88x faster than extractPages (1 page from 2000-page PDF)

### Split into single-page PDFs

| Benchmark                   | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------------------- | ------: | -------: | -------: | -----: | ------: |
| split 100-page PDF (0.1MB)  |    24.4 |  41.06ms |  43.64ms | ±1.56% |      13 |
| split 2000-page PDF (0.9MB) |     1.3 | 742.21ms | 742.21ms | ±0.00% |       1 |

- **split 100-page PDF (0.1MB)** is 18.08x faster than split 2000-page PDF (0.9MB)

### Batch page extraction

| Benchmark                                              | ops/sec |    Mean |     p99 |    RME | Samples |
| :----------------------------------------------------- | ------: | ------: | ------: | -----: | ------: |
| extract first 10 pages from 2000-page PDF              |    17.2 | 58.28ms | 60.74ms | ±1.38% |       9 |
| extract first 100 pages from 2000-page PDF             |    16.3 | 61.54ms | 62.94ms | ±1.35% |       9 |
| extract every 10th page from 2000-page PDF (200 pages) |    14.9 | 67.08ms | 67.57ms | ±0.63% |       8 |

- **extract first 10 pages from 2000-page PDF** is 1.06x faster than extract first 100 pages from 2000-page PDF
- **extract first 10 pages from 2000-page PDF** is 1.15x faster than extract every 10th page from 2000-page PDF (200 pages)

---

_Results are machine-dependent. Use for relative comparison only._
