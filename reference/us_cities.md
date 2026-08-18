# City locations and populations (historical and contemporary)

This function returns an `sf` object of cities (or populated places)
with their populations and latitudes and longitudes. Population data is
taken from the U.S. Census.

## Usage

``` r
us_cities(map_date = NULL, states = NULL)
```

## Arguments

- map_date:

  If `NULL`, then city populations from the 2010 census (the most recent
  census) are returned. This parameter accepts a `Date` object or a
  character string coercible to a `Date` object, as well as numeric
  values representing a year. If a year or date is used, then city
  populations from the decennial census from 1790 to 2010 *prior* to
  that year is returned. For example, `1805` or `"1805-07-04"` would
  return city populations from the 1800 census.

- states:

  A character vector of state or territory names or abbreviations. Only
  boundaries for those states/territories will be returned. If `NULL`,
  all boundaries will be returned.

## Value

An `sf` object.

## References

The data was compiled by Erik Steiner and Jason Heppler at the Center
for Spatial and Textual Analysis, Stanford University. See their [the
description of the
data](https://github.com/cestastanford/historical-us-city-populations)
for a fuller accounting of how the data was gathered.

## Examples

``` r
if (require(USAboundariesData, quietly = TRUE)) {
  us_cities(1805)
  us_cities("1828-05-08")
  us_cities()
}
#> City populations for contemporary data come from the 2010 census.
#> Simple feature collection with 6932 features and 12 fields
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: -166.5251 ymin: 19.09679 xmax: -67.23919 ymax: 71.25408
#> Geodetic CRS:  WGS 84
#> # A tibble: 6,932 × 13
#>    city      state_name state_abbr county    county_name stplfips_2010 name_2010
#>    <chr>     <chr>      <chr>      <chr>     <chr>       <chr>         <chr>    
#>  1 Anchorage Alaska     AK         THIRD JU… Third Judi… 0203000       Anchorag…
#>  2 Barrow    Alaska     AK         North Sl… North Slop… 0205200       Barrow c…
#>  3 Bethel    Alaska     AK         Bethel C… Bethel Cen… 0206520       Bethel c…
#>  4 Fairbanks Alaska     AK         FOURTH J… Fourth Jud… 0224230       Fairbank…
#>  5 Homer     Alaska     AK         Kenai Pe… Kenai Peni… 0233140       Homer ci…
#>  6 Juneau    Alaska     AK         FIRST JU… First Judi… 0236400       Juneau c…
#>  7 Kenai     Alaska     AK         Kenai Pe… Kenai Peni… 0238420       Kenai ci…
#>  8 Ketchikan Alaska     AK         FIRST JU… First Judi… 0238970       Ketchika…
#>  9 Kodiak    Alaska     AK         Kodiak I… Kodiak Isl… 0240950       Kodiak c…
#> 10 Kotzebue  Alaska     AK         Northwes… Northwest … 0241830       Kotzebue…
#> # ℹ 6,922 more rows
#> # ℹ 6 more variables: city_source <chr>, population_source <chr>,
#> #   place_type <chr>, year <int>, population <int>, geometry <POINT [°]>
```
