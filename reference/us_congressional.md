# Congressional district boundaries (contemporary)

Get the current (2024) boundaries for U.S. Congressional districts.

## Usage

``` r
us_congressional(resolution = c("low", "high"), states = NULL)
```

## Arguments

- resolution:

  The resolution of the boundaries.

- states:

  A character vector of state or territory names. Only boundaries inside
  these states/territories will be returned. If `NULL`, all boundaries
  will be returned.

## Value

An `sf` object.

## See also

For documentation of and citation to the underlying shapefiles for
contemporary data from the U.S. Census Bureau, see the
`census_boundaries` help file in the USAboundariesData package.

## Examples

``` r
if (require(USAboundariesData, quietly = TRUE) && require(sf, quietly = TRUE)) {
  us_congressional <- us_congressional()
  va_congressional <- us_congressional(
    states = "Virginia", resolution = "high")
  plot(st_geometry(us_congressional))
  plot(st_geometry(va_congressional))
}


```
