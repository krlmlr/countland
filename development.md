# countland Development

## Development in python

To install from local source:

    conda create -n countland -c conda-forge python==3.10
    conda activate countland
    cd countland-py
    pip install .[dev]
    pip install jupyter

This will reload countland functions (e.g. after an edit)

    import importlib
    importlib.reload(countland)

To run tests for  `countland-py/`:

    conda activate countland
    python -m pytest

## Development in R

### Loading and packaging

This package is built with the excellent [devtools](https://github.com/hadley/devtools). Extensive explanations on using devtools
to create R packages is available in the book
[R Packages](http://r-pkgs.had.co.nz/).

Development typically involves `cd`ing to the package directory `countland-R/`, launching R, and running some combination of the following:

	options(error=traceback) # Get line numbers for errors
    library(devtools)
    load_all()
    test()
    document()
    check() # A wrapper for R CMD check, see http://r-pkgs.had.co.nz/check.html#check
    build() # Create package bundle, including executed vignettes

To regenerate the pdf manual, run the following shell command in the package directory:

    R CMD Rd2pdf . --force --output=countland-manual.pdf

### Vignettes

Construction of vignettes follows https://r-pkgs.org/vignettes.html .