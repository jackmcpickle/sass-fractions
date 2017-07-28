# Sass Fractions

[![Build Status](https://travis-ci.org/jackmcpickle/sass-fractions.svg?branch=master)](https://travis-ci.org/jackmcpickle/sass-fractions)

Converts fractions to words or lowest common denominator

## Install

`npm install sass-fractions`

or

`yarn add sass-fractions`

## Function - fraction-names()

`fraction-names($numerator, $denominator, $separator, $lowest-common-denominator)`

Returns the fraction passed into words

`$separator` -  character(s) to separate the worded fraction, default: '-'

`$lowest-common-denominator` - Whether or not to convert the fraction into it's lowest common denominator, default: true

### Usage - fraction to words as lowest common denominator

Create a simple grid

```scss
.grid-#{fraction-names(2, 3)} {
  width: percentage(2 / 3);
}
```
Outputs

```css
.grid-two-thirds {
  width: 66.66666%;
}
```

### Usage - fractions to words without converting

```scss
$lowest-common-denominator: false;

.grid-#{fraction-names(4, 12, '_')} {
  width: percentage(4 / 12);
}
```

Outputs

```css
.grid_four_twelfths {
  width: 33.33333%;
}
```

## Function - lowest-fraction()

`lowest-fraction($numerator, $denominator, $separator)`

Returns the fraction passed into it's lowest common denominator.

`$separator` -  character(s) to separate the fraction words, default: '-'


### Usage - fraction to lowest common denominator

```scss
.grid-#{lowest-fraction(5, 10)} {
  width: percentage(5 / 10);
}
```

Outputs 

```css
.grid-1-2 {
  width: 50%;
}
```

## Multilingual

Change the default `$single-fraction-names` and `$digit-names`

```scss
// Spanish / Español
$single-fraction-names: (1: todo, 2: mitad, 3: tercio);
$digit-names: (1: uno, 2: dos);

.grid-#{fraction-names(2, 3)} {
  width: percentage(2 / 3);
}

```

Outputs

```css
.grid-dos-tercios {
  width: 66.66666%;
}
```
