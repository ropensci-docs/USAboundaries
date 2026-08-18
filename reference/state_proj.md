# Data for projections from the State Plane Coordinate System

This data frame includes state abbreviations, EPSG codes, and proj4
strings for projections from the State Plane Coordinate System.

## Usage

``` r
state_proj
```

## Format

A data frame with 123 rows and 5 variables:

- state:

  The state or territory abbreviation.

- zone:

  Name of the state plane zone.

- epsg:

  The EPSG code for each state plane zone.

- proj4_string:

  The PROJ4 string for the state plane projection.

- statewide_proj:

  State plane zone for projecting the entire state.

## References

[State Plane Coordinate
System](https://en.wikipedia.org/wiki/State_Plane_Coordinate_System)
