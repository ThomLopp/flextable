flextable R package
================

<!-- README.md is generated from README.Rmd. Please edit that file -->

[![R build
status](https://github.com/davidgohel/flextable/workflows/R-CMD-check/badge.svg)](https://github.com/davidgohel/flextable/actions)
[![version](https://www.r-pkg.org/badges/version/flextable)](https://CRAN.R-project.org/package=flextable)
![Active](https://www.repostatus.org/badges/latest/active.svg)

The flextable package provides a framework for easily create tables for
reporting and publications. Tables can be easily formatted with a set of
verbs such as `bold()`, `color()`, they can receive a header of more
than one line, cells can be merged or contain an image. The package make
it possible to build any table for publication from a `data.frame` and
provides sugar function `as_flextable()` to convert several R objects to
a flextable, such as an object return from `table()` or a model.

``` r
set_flextable_defaults(
  font.family = "Arial", font.size = 10, 
  border.color = "gray")

flextable(head(cars)) %>% 
  bold(part = "header") %>% 
  add_footer_lines("The 'cars' dataset")

ggplot2::diamonds |> 
  with(table(cut, color)) |> 
  as_flextable()
```

Tables can be embedded within HTML, PDF, Word and PowerPoint documents
from R Markdown documents and within RTF or Microsoft Word or PowerPoint
documents with package officer. Tables can also be rendered as R plots
or graphic files (png).

<img src="man/figures/fig_formats.png" width="170px" alt="flextable formats" align="center" />

``` r
flextable(mtcars) %>% 
  theme_vanilla() %>% 
  save_as_docx(path = "mytable.docx")
```

A `flextable` object is a data.frame representation. An API is available
to let R users create tables for reporting and control their formatting
properties and their layout. The package provides functions that give
control over:

- header, body and footer content
- text, paragraphs, cells and border formatting of any element
- displayed values

The package also offers a set of high-level functions that allow tabular
reporting of statistical models and the creation of complex cross
tabulations.

## Installation

``` r
install.packages("flextable")
```

You can get the development version from GitHub:

``` r
devtools::install_github("davidgohel/flextable")
```

## Resources

- User guide: <https://ardata-fr.github.io/flextable-book/>
- Manuals: <https://davidgohel.github.io/flextable/reference/index.html>
- Gallery of examples: <https://ardata.fr/en/flextable-gallery/>

### Getting help / questions

If you have questions about how to use the package, visit Stackoverflow
and use tags `flextable` and `r` [Stackoverflow
link](https://stackoverflow.com/questions/tagged/flextable+r). You can
also use <https://github.com/davidgohel/flextable/discussions> to start
a discussion.

### Bug reports

When you file a [bug
report](https://github.com/davidgohel/flextable/issues), please spend
some time making it easy for us to reproduce. If you take the time to
make the bug report consistent, it will be easier to fix.
