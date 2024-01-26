
# somatemplate <a href="https://somalogic.github.io/somatemplate"><img src="man/figures/logo.png" align="right" height="138" alt="somatemplate website" /></a>

## Overview

`somatemplate` provides a custom
[pkgdown](https://pkgdown.r-lib.org/index.html) template for SomaLogic’s
R packages. This package is designed to provide a cohesive visual
identity for packages developed by SomaLogic, and we kindly request that
you do not use it for your own personal package.

`somatemplate` was inspired primarily by
[tidytemplate](https://tidytemplate.tidyverse.org/) and
[rotemplate](https://docs.ropensci.org/rotemplate/).

## Installation

`somatemplate` is not currently available to the public, i.e. it is a
private/internal GitHub repo. To install the package, it must be cloned
and installed locally:

``` bash
git clone git@github.com:SomaLogic/somatemplate.git
```

``` r
install.packages("<filepath to somatemplate>", repos = NULL, type = "source")
```

Once made public, `somatemplate` can be installed from GitHub as
follows:

``` r
remotes::install_github("SomaLogic/somatemplate")
```

## <a id="usage"></a>Usage

To use `somatemplate` for a `pkgdown` site, ensure that the package is
installed, and that the `DESCRIPTION` contains the following line:

``` r
Config/Needs/website: SomaLogic/somatemplate
```

Then, insert the following code into the pkgdown config file,
`_pkgdown.yml` (or create a new one, if it doesn’t exist already):

``` r
template:
  package: somatemplate
  bootstrap: 5
```

If you’re updating a previously made pkgdown config file to use
`somatemplate`, use the following list to enable use of the template:

- Run `usethis::use_pkgdown_github_pages()`
- Update `DESCRIPTION` to include
  `Config/Needs/website: SomaLogic/somatemplate`, as described in
  [Usage](#usage) above
- Update `_pkgdown.yml` to reference `somatemplate`, as described above
- Optional: Update the `NEWS.md` file to describe use of `somatemplate`

## Package Structure

This `pkgdown` template appears to be structured like a normal R
package, but differs in a few key ways:

    --- inst
        |__pkgdown
           |__ _pkgdown.yml    # Configuration YAML file for pkgdown site, including customized sidebar links
           |__templates        # Custom HTML templates that override pkgdown defaults
              |__footer.html
           |__extra.scss       # Extra SCSS code that will be copied into the rendered site
    --- R
        |__test-function.R.    # Example R function for template testing purposes only
    --- vignettes
        |__test-code.Rmd       # Example vignette for template testing purposes only
        |__test-formatting.Rmd # Example vignette for template testing purposes only