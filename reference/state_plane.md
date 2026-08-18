# Projections from the State Plane Coordinate System

Get EPSG codes or PROJ.4 codes for projections from the [State Plane
Coordinate
System](https://en.wikipedia.org/wiki/State_Plane_Coordinate_System).

## Usage

``` r
state_plane(state, plane_id = NULL, type = c("epsg", "proj4"))
```

## Arguments

- state:

  The postal code for the state.

- plane_id:

  The state plane geographic zone identifier. A `NULL` value will return
  a projection for the entire state.

- type:

  The type of output to return: either an EPSG code or PROJ4 string.

## Value

Either a PROJ4 string as a character vector or an EPSG code as an
integer.

## See also

For documentation of the underlying State Plane Coordinate System
projection data frame, see
[`state_proj`](https://docs.ropensci.org/USAboundaries/reference/state_proj.md).

## Examples

``` r
if (require(USAboundariesData, quietly = TRUE)) {
  state_plane(state = "MA", type = "epsg")
  state_plane(state = "MA", type = "proj4")
  state_plane(state = "MA", plane_id = "island", type = "epsg")
  state_plane(state = "MA", plane_id = "island", type = "proj4")

  # Show the difference made by a state plane projection
  if (require(sf, quietly = TRUE)) {
    va <- us_states(states = "VA", resolution = "high")
    plot(st_geometry(va), graticule = TRUE)
    va <- st_transform(va, state_plane("VA"))
    plot(st_geometry(va), graticule = TRUE)
  }
}
#> Warning: package ‘USAboundariesData’ was built under R version 4.6.1
#> Linking to GEOS 3.12.1, GDAL 3.8.4, PROJ 9.4.0; sf_use_s2() is TRUE


```
