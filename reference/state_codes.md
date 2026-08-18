# State codes and abbreviations for U.S. states and territories

This data frame includes abbreviations and codes for states and
territories in the United States. It is intended as a lookup table.

## Usage

``` r
state_codes
```

## Format

A data.frame with 69 rows and 4 variables:

- state_name:

  The state or territory name

- state_abbr:

  The two character abbreviation for the state or territory.

- state_code:

  A 3-digit numeric FIPS code for the state or territory.

- jurisdiction_type:

  One of `state`, `territory`, or `district`.

## References

U.S. Census Bureau, [Ameri. National Standards Institute (ANSI), Federal
Information Processing Series (FIPS), and Other Standardized Geographic
Codes](https://www.census.gov/library/reference/code-lists/ansi.html)
U.S. Census Bureau (2025).
