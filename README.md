# Sass Fractions

[![Build Status](https://travis-ci.org/jackmcpickle/sass-fractions.svg?branch=master)](https://travis-ci.org/jackmcpickle/sass-fractions)

Converts fractions to words or lowest common denominator

## Install

`npm install sass-fractions`

or

`yarn add sass-fractions`

## Function - wfrac()

`wfrac($numerator, $denominator, $separator: '-', $lowest-common-denominator: true)`

Returns the fraction passed into words

`$separator` -  character(s) to separate the worded fraction, default: '-'

`$lowest-common-denominator` - Whether or not to convert the fraction into it's lowest common denominator, default: true

### Usage - fraction to words as lowest common denominator

Create a simple grid

```scss
.grid-#{wfrac(2, 3)} {
  /* properties... */
}
```
Outputs

```css
.grid-two-thirds {
  /* properties... */
}
```

### Usage - fractions to words without converting

```scss
$lowest-common-denominator: false;
.grid-#{wfrac(4, 12, '_')} {
  /* properties... */
}
```

Outputs

```css
.grid_four_twelfths {
  /* properties... */
}
```

## Function - lfrac()

`lfrac($numerator, $denominator, $separator: '-')`

Returns the fraction passed into it's lowest common denominator.

`$separator` -  character(s) to separate the fraction words, default: '-'


### Usage - fraction to lowest common denominator

```scss
.grid-#{lfrac(5, 10)} {
  /* properties... */
}
```

Outputs 

```css
.grid-1-2 {
  /* properties... */
}
```

## Multilingual

Change the default `$single-fraction-names` and `$digit-names`

```scss
// Spanish / Español
$single-fraction-names: (todo, mitad, tercio);
$digit-names: (uno, dos);

.grid-#{wfrac(2, 3)} {
  /* properties... */
}

```

Outputs

```css
.grid-dos-tercios {
  /* properties... */
}
```

## Function - frac2word()

`frac2word($string, $separator: '/', $fraction-separator: '-', $lowest-common-denominator: true)`

Parses the fraction as a string - returns the fraction passed into words.

`$separator` -  character(s) that is used to separate the fraction string, default: '/'

`$fraction-separator` - character(s) to separate the fraction words that are returned.

`$lowest-common-denominator` - Whether or not to convert the fraction into it's lowest common denominator, default: true

```scss
.grid-#{frac2word('2/12')} {
  /* properties... */
}
```

Outputs

```css
.grid-one-sixth {
  /* properties... */
}
```

## Function - frac2low()

`frac2low($string, $separator: '/', $fraction-separator: '-')`

Parses the fraction as a string - returns the fraction in its lowest common denominator form

`$separator` -  character(s) that is used to separate the fraction string, default: '/'

`$fraction-separator` - character(s) to separate the fraction words that are returned.

```scss
.grid-#{frac2low('2/12')} {
  /* properties... */
}
```

Outputs

```css
.grid-1-6 {
  /* properties... */
}
```
