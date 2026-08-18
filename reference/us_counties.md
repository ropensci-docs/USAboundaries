# County boundaries (contemporary and historical)

Get the current (2024) boundaries for U.S counties from the U.S. Census
Bureau, or get historical county boundaries for dates between 30
December 1636 and 31 December 2000.

## Usage

``` r
us_counties(map_date = NULL, resolution = c("low", "high"), states = NULL)
```

## Arguments

- map_date:

  The date of the boundaries as some object coercible to a date with
  [`as.Date()`](https://rdrr.io/r/base/as.Date.html); the easiest option
  is a character vector following the [ISO
  8601](https://en.wikipedia.org/wiki/ISO_8601) data format. If `NULL`
  (the default) the contemporary boundaries will be returned.

- resolution:

  The resolution of the map.

- states:

  A character vector of state or territory names or abbreviations. Only
  boundaries for those states/territories will be returned. If `NULL`,
  all boundaries will be returned.

## Value

An `sf` object.

## See also

For documentation of and citation to the underlying shapefiles for
contemporary data from the U.S. Census Bureau, see the
`census_boundaries` help file in the USAboundariesData package. For
documentation of and citation to the underlying shapefiles for
historical data from the Atlas of Historical County Boundaries, see the
`ahcb_boundaries` help file in the USAboundariesData package.

## Examples

``` r
if (require(USAboundariesData, quietly = TRUE) && require(sf, quietly = TRUE)) {
  contemporary_us <- us_counties()
  historical_us <- us_counties("1820-07-04")
  contemporary_ne <- us_counties(
    states = c(
      "Massachusetts",
      "Vermont",
      "Maine",
      "New Hampshire",
      "Rhode Island",
      "Connecticut"
    )
  )
  historical_ne <- us_counties(
    "1803-04-28",
    states = c(
      "Massachusetts",
      "Vermont",
      "Maine",
      "New Hampshire",
      "Rhode Island",
      "Connecticut"
    ),
    resolution = "high"
  )

  plot(st_geometry(contemporary_us))
  plot(st_geometry(historical_us))
  plot(st_geometry(contemporary_ne))
  plot(st_geometry(historical_ne))
}




```
