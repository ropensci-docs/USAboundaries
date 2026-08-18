# Zip Code Tabulation Areas (contemporary)

Get the current (2019) centroids for U.S Zipcode Tabulation Areas from
the U.S. Census Bureau. The centroids were calculated from the ZCTA
boundary files available on the U.S. Census Bureau website.

## Usage

``` r
us_zipcodes()
```

## Value

An `sf` object.

## See also

For documentation of and citation to the underlying shapefiles for
contemporary data from the U.S. Census Bureau, see the
`census_boundaries` documentation in the USAboundariesData package.

## Examples

``` r
if (require(USAboundariesData, quietly = TRUE)) {
  us_zipcodes()
}
#> Simple feature collection with 33144 features and 6 fields
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: -176.6314 ymin: -14.22075 xmax: 145.7536 ymax: 71.27382
#> Geodetic CRS:  WGS 84
#> First 10 features:
#>    zipcode zcta5ce10     affgeoid10 geoid10    aland10 awater10
#> 1    35586     35586 8600000US35586   35586  472581657   892816
#> 2    72454     72454 8600000US72454   72454  263532032   775633
#> 3    71653     71653 8600000US71653   71653  817752215 89308151
#> 4    19963     19963 8600000US19963   19963  276290156 21123546
#> 5    81303     81303 8600000US81303   81303  557450510  6445737
#> 6    81640     81640 8600000US81640   81640 6160477420 11658548
#> 7    06243     06243 8600000US06243   06243     903761   257961
#> 8    06060     06060 8600000US06060   06060   31260792     2582
#> 9    93924     93924 8600000US93924   93924  491763193  1100383
#> 10   34113     34113 8600000US34113   34113   72733092 16053633
#>                      geometry
#> 1  POINT (-88.13867 33.87678)
#> 2  POINT (-90.20791 36.40115)
#> 3  POINT (-91.25755 33.34129)
#> 4   POINT (-75.3816 38.93615)
#> 5  POINT (-107.8911 37.11649)
#> 6  POINT (-108.5192 40.65927)
#> 7  POINT (-71.80244 41.84523)
#> 8  POINT (-72.84569 42.00703)
#> 9    POINT (-121.6407 36.399)
#> 10 POINT (-81.72777 26.04869)
```
