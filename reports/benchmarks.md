# Benchmark Report

> Generated on 2026-09-14 at 11:51:18 UTC
>
> System: linux | AMD EPYC 9V74 80-Core Processor (4 cores) | 16GB RAM | Bun 1.4.2
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
| libpdf          |    53.2 |  18.81ms |  19.99ms | ±1.46% |      27 |
| @cantoo/pdf-lib |     4.7 | 213.58ms | 221.02ms | ±1.44% |      10 |
| pdf-lib         |     4.6 | 216.77ms | 225.42ms | ±1.41% |      10 |

- **libpdf** is 11.35x faster than @cantoo/pdf-lib
- **libpdf** is 11.52x faster than pdf-lib

### Create blank PDF

| Benchmark       | ops/sec |  Mean |    p99 |    RME | Samples |
| :-------------- | ------: | ----: | -----: | -----: | ------: |
| libpdf          |   16.0K |  62us |  161us | ±4.49% |   8,009 |
| pdf-lib         |    2.9K | 346us | 1.47ms | ±3.29% |   1,445 |
| @cantoo/pdf-lib |    2.3K | 433us | 1.62ms | ±3.01% |   1,155 |

- **libpdf** is 5.54x faster than pdf-lib
- **libpdf** is 6.94x faster than @cantoo/pdf-lib

### Add 10 pages

| Benchmark       | ops/sec |  Mean |    p99 |    RME | Samples |
| :-------------- | ------: | ----: | -----: | -----: | ------: |
| libpdf          |    9.1K | 110us |  199us | ±1.20% |   4,539 |
| @cantoo/pdf-lib |    2.5K | 404us | 2.22ms | ±3.69% |   1,239 |
| pdf-lib         |    2.4K | 409us | 1.84ms | ±3.36% |   1,225 |

- **libpdf** is 3.67x faster than @cantoo/pdf-lib
- **libpdf** is 3.71x faster than pdf-lib

### Draw 50 rectangles

| Benchmark       | ops/sec |   Mean |     p99 |    RME | Samples |
| :-------------- | ------: | -----: | ------: | -----: | ------: |
| libpdf          |    2.9K |  345us |  1.13ms | ±2.02% |   1,450 |
| pdf-lib         |   701.7 | 1.43ms |  7.06ms | ±8.59% |     351 |
| @cantoo/pdf-lib |   523.4 | 1.91ms | 10.69ms | ±9.36% |     263 |

- **libpdf** is 4.13x faster than pdf-lib
- **libpdf** is 5.54x faster than @cantoo/pdf-lib

### Load and save PDF

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| libpdf          |    49.4 |  20.23ms |  34.06ms | ±6.95% |      25 |
| pdf-lib         |     3.1 | 321.14ms | 339.69ms | ±2.11% |      10 |
| @cantoo/pdf-lib |     1.9 | 540.43ms | 555.77ms | ±1.07% |      10 |

- **libpdf** is 15.87x faster than pdf-lib
- **libpdf** is 26.71x faster than @cantoo/pdf-lib

### Load, modify, and save PDF

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| pdf-lib         |     3.2 | 315.52ms | 328.51ms | ±1.23% |      10 |
| libpdf          |     2.9 | 340.41ms | 354.99ms | ±1.33% |      10 |
| @cantoo/pdf-lib |     1.9 | 539.03ms | 555.98ms | ±1.17% |      10 |

- **pdf-lib** is 1.08x faster than libpdf
- **pdf-lib** is 1.71x faster than @cantoo/pdf-lib

### Extract single page from 100-page PDF

| Benchmark       | ops/sec |   Mean |     p99 |    RME | Samples |
| :-------------- | ------: | -----: | ------: | -----: | ------: |
| libpdf          |   290.2 | 3.45ms |  4.35ms | ±1.66% |     146 |
| pdf-lib         |   115.0 | 8.70ms | 10.63ms | ±1.66% |      58 |
| @cantoo/pdf-lib |   110.8 | 9.03ms | 10.45ms | ±1.79% |      56 |

- **libpdf** is 2.52x faster than pdf-lib
- **libpdf** is 2.62x faster than @cantoo/pdf-lib

### Split 100-page PDF into single-page PDFs

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    26.9 | 37.24ms | 41.17ms | ±2.09% |      14 |
| pdf-lib         |    14.7 | 68.19ms | 72.96ms | ±4.74% |       8 |
| @cantoo/pdf-lib |    12.9 | 77.23ms | 85.47ms | ±6.51% |       7 |

- **libpdf** is 1.83x faster than pdf-lib
- **libpdf** is 2.07x faster than @cantoo/pdf-lib

### Split 2000-page PDF into single-page PDFs (0.9MB)

| Benchmark       | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------- | ------: | -------: | -------: | -----: | ------: |
| libpdf          |     1.4 | 702.37ms | 702.37ms | ±0.00% |       1 |
| pdf-lib         |   0.772 |    1.30s |    1.30s | ±0.00% |       1 |
| @cantoo/pdf-lib |   0.719 |    1.39s |    1.39s | ±0.00% |       1 |

- **libpdf** is 1.85x faster than pdf-lib
- **libpdf** is 1.98x faster than @cantoo/pdf-lib

### Copy 10 pages between documents

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |   232.5 |  4.30ms |  5.52ms | ±1.32% |     117 |
| pdf-lib         |    88.1 | 11.35ms | 13.60ms | ±1.63% |      45 |
| @cantoo/pdf-lib |    77.7 | 12.87ms | 14.09ms | ±1.63% |      39 |

- **libpdf** is 2.64x faster than pdf-lib
- **libpdf** is 2.99x faster than @cantoo/pdf-lib

### Merge 2 x 100-page PDFs

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    62.9 | 15.90ms | 26.72ms | ±5.89% |      32 |
| pdf-lib         |    19.2 | 52.02ms | 54.72ms | ±1.88% |      10 |
| @cantoo/pdf-lib |    16.1 | 62.29ms | 63.44ms | ±1.00% |       9 |

- **libpdf** is 3.27x faster than pdf-lib
- **libpdf** is 3.92x faster than @cantoo/pdf-lib

### Fill FINTRAC form fields

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    47.7 | 20.98ms | 38.33ms | ±8.73% |      24 |
| pdf-lib         |    37.2 | 26.90ms | 39.02ms | ±5.92% |      19 |
| @cantoo/pdf-lib |    36.6 | 27.35ms | 40.32ms | ±6.39% |      19 |

- **libpdf** is 1.28x faster than pdf-lib
- **libpdf** is 1.30x faster than @cantoo/pdf-lib

### Fill and flatten FINTRAC form

| Benchmark       | ops/sec |    Mean |     p99 |    RME | Samples |
| :-------------- | ------: | ------: | ------: | -----: | ------: |
| libpdf          |    62.3 | 16.06ms | 19.76ms | ±2.72% |      32 |
| pdf-lib         |  FAILED |       - |       - |      - |       0 |
| @cantoo/pdf-lib |    32.9 | 30.40ms | 45.60ms | ±6.85% |      17 |

- **libpdf** is 1.89x faster than @cantoo/pdf-lib

## Copying

### Copy pages between documents

| Benchmark                       | ops/sec |   Mean |    p99 |    RME | Samples |
| :------------------------------ | ------: | -----: | -----: | -----: | ------: |
| copy 1 page                     |   959.3 | 1.04ms | 1.98ms | ±2.43% |     480 |
| copy 10 pages from 100-page PDF |   226.6 | 4.41ms | 7.02ms | ±2.23% |     114 |
| copy all 100 pages              |   124.7 | 8.02ms | 8.64ms | ±0.87% |      63 |

- **copy 1 page** is 4.23x faster than copy 10 pages from 100-page PDF
- **copy 1 page** is 7.70x faster than copy all 100 pages

### Duplicate pages within same document

| Benchmark                                 | ops/sec |  Mean |    p99 |    RME | Samples |
| :---------------------------------------- | ------: | ----: | -----: | -----: | ------: |
| duplicate all pages (double the document) |    1.1K | 948us | 1.40ms | ±0.81% |     528 |
| duplicate page 0                          |    1.1K | 952us | 1.49ms | ±0.97% |     526 |

- **duplicate all pages (double the document)** is 1.00x faster than duplicate page 0

### Merge PDFs

| Benchmark               | ops/sec |    Mean |     p99 |    RME | Samples |
| :---------------------- | ------: | ------: | ------: | -----: | ------: |
| merge 2 small PDFs      |   682.9 |  1.46ms |  2.02ms | ±1.13% |     342 |
| merge 10 small PDFs     |   127.1 |  7.87ms | 10.81ms | ±1.47% |      64 |
| merge 2 x 100-page PDFs |    70.6 | 14.15ms | 15.49ms | ±1.19% |      36 |

- **merge 2 small PDFs** is 5.37x faster than merge 10 small PDFs
- **merge 2 small PDFs** is 9.67x faster than merge 2 x 100-page PDFs

## Drawing

| Benchmark                           | ops/sec |   Mean |    p99 |    RME | Samples |
| :---------------------------------- | ------: | -----: | -----: | -----: | ------: |
| draw 100 lines                      |    1.8K |  543us | 1.13ms | ±1.26% |     921 |
| draw 100 rectangles                 |    1.7K |  601us | 1.24ms | ±1.70% |     833 |
| draw 100 circles                    |    1.1K |  902us | 1.81ms | ±1.69% |     555 |
| create 10 pages with mixed content  |   687.2 | 1.46ms | 2.52ms | ±2.03% |     344 |
| draw 100 text lines (standard font) |   566.5 | 1.77ms | 3.61ms | ±2.95% |     284 |

- **draw 100 lines** is 1.11x faster than draw 100 rectangles
- **draw 100 lines** is 1.66x faster than draw 100 circles
- **draw 100 lines** is 2.68x faster than create 10 pages with mixed content
- **draw 100 lines** is 3.25x faster than draw 100 text lines (standard font)

## Forms

| Benchmark         | ops/sec |    Mean |     p99 |    RME | Samples |
| :---------------- | ------: | ------: | ------: | -----: | ------: |
| read field values |   376.4 |  2.66ms |  4.86ms | ±2.52% |     189 |
| get form fields   |   348.7 |  2.87ms |  4.81ms | ±2.62% |     175 |
| flatten form      |   131.5 |  7.61ms |  8.30ms | ±0.95% |      66 |
| fill text fields  |    84.8 | 11.80ms | 15.57ms | ±4.18% |      43 |

- **read field values** is 1.08x faster than get form fields
- **read field values** is 2.86x faster than flatten form
- **read field values** is 4.44x faster than fill text fields

## Loading

| Benchmark              | ops/sec |    Mean |     p99 |    RME | Samples |
| :--------------------- | ------: | ------: | ------: | -----: | ------: |
| load small PDF (888B)  |   19.1K |    52us |   161us | ±1.95% |   9,529 |
| load medium PDF (19KB) |   12.4K |    80us |   106us | ±0.55% |   6,225 |
| load form PDF (116KB)  |   834.9 |  1.20ms |  2.26ms | ±1.45% |     418 |
| load heavy PDF (2.0MB) |    53.1 | 18.84ms | 27.22ms | ±3.80% |      27 |

- **load small PDF (888B)** is 1.53x faster than load medium PDF (19KB)
- **load small PDF (888B)** is 22.83x faster than load form PDF (116KB)
- **load small PDF (888B)** is 359.06x faster than load heavy PDF (2.0MB)

## Saving

| Benchmark                          | ops/sec |    Mean |     p99 |    RME | Samples |
| :--------------------------------- | ------: | ------: | ------: | -----: | ------: |
| save unmodified (19KB)             |   10.3K |    97us |   280us | ±3.04% |   5,157 |
| incremental save (19KB)            |    7.3K |   137us |   289us | ±1.18% |   3,640 |
| save with modifications (19KB)     |    1.3K |   771us |  1.40ms | ±1.65% |     649 |
| save heavy PDF (2.0MB)             |    52.8 | 18.92ms | 20.64ms | ±1.52% |      27 |
| incremental save heavy PDF (2.0MB) |    50.9 | 19.66ms | 20.98ms | ±1.27% |      26 |

- **save unmodified (19KB)** is 1.42x faster than incremental save (19KB)
- **save unmodified (19KB)** is 7.95x faster than save with modifications (19KB)
- **save unmodified (19KB)** is 195.15x faster than save heavy PDF (2.0MB)
- **save unmodified (19KB)** is 202.75x faster than incremental save heavy PDF (2.0MB)

## Splitting

### Extract single page

| Benchmark                                | ops/sec |    Mean |     p99 |    RME | Samples |
| :--------------------------------------- | ------: | ------: | ------: | -----: | ------: |
| extractPages (1 page from small PDF)     |   990.8 |  1.01ms |  1.91ms | ±2.17% |     496 |
| extractPages (1 page from 100-page PDF)  |   298.0 |  3.36ms |  4.00ms | ±1.16% |     149 |
| extractPages (1 page from 2000-page PDF) |    18.6 | 53.68ms | 68.77ms | ±7.10% |      10 |

- **extractPages (1 page from small PDF)** is 3.32x faster than extractPages (1 page from 100-page PDF)
- **extractPages (1 page from small PDF)** is 53.18x faster than extractPages (1 page from 2000-page PDF)

### Split into single-page PDFs

| Benchmark                   | ops/sec |     Mean |      p99 |    RME | Samples |
| :-------------------------- | ------: | -------: | -------: | -----: | ------: |
| split 100-page PDF (0.1MB)  |    26.7 |  37.48ms |  42.37ms | ±2.51% |      14 |
| split 2000-page PDF (0.9MB) |     1.5 | 675.99ms | 675.99ms | ±0.00% |       1 |

- **split 100-page PDF (0.1MB)** is 18.04x faster than split 2000-page PDF (0.9MB)

### Batch page extraction

| Benchmark                                              | ops/sec |    Mean |     p99 |    RME | Samples |
| :----------------------------------------------------- | ------: | ------: | ------: | -----: | ------: |
| extract first 10 pages from 2000-page PDF              |    18.4 | 54.23ms | 55.52ms | ±1.10% |      10 |
| extract first 100 pages from 2000-page PDF             |    17.2 | 58.13ms | 59.68ms | ±1.50% |       9 |
| extract every 10th page from 2000-page PDF (200 pages) |    15.9 | 62.87ms | 63.94ms | ±0.94% |       8 |

- **extract first 10 pages from 2000-page PDF** is 1.07x faster than extract first 100 pages from 2000-page PDF
- **extract first 10 pages from 2000-page PDF** is 1.16x faster than extract every 10th page from 2000-page PDF (200 pages)

---

_Results are machine-dependent. Use for relative comparison only._
