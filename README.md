# is-vegan

Is-Vegan helps you to find out which food ingredients are vegan / non-vegan. It can answer that on 1 ingredient or on a list of ingredients. It uses the 600+ entries black list of non-vegan ingredients.

[How to use?](#usage)

## Sources

We want to make sure that you understand how is-vegan is implemented. We analyzed as many good information websites for vegan / non-vegan ingredients as we found to get a very accurate list of ingredients. However, feel free to send a pull request with an updated version of the list.

Websites we parsed:

* [veganwolf](http://www.veganwolf.com/animal_ingredients.htm)
* [peta](https://www.peta.org/living/food/animal-ingredients-list/)
* [veganpeace](http://www.veganpeace.com/ingredients/ingredients.htm)

**and we added also a few ourselves...**

## Usage

### Add

`yarn add is-vegan`

or

`npm install is-vegan --save`

### example

```javascript
const isVegan = require('is-vegan');

// or

import * as isVegan from 'is-vegan';

// example for single ingredient
isVegan.isVeganIngredient('soy'); // true
isVegan.isVeganIngredient('milk'); // false

// example for list of ingredients
isVegan.isVeganIngredientList(['aspic', 'albumin']); // false
isVegan.isVeganIngredientList(['soy', 'cacao butter']); // true

// or

import { isVeganIngredient, isVeganIngredientList } from 'is-vegan';

// example for single ingredient
isVeganIngredient('soy'); // true
isVeganIngredient('milk'); // false

// example for list of ingredients
isVeganIngredientList(['aspic', 'albumin']); // false
isVeganIngredientList(['soy', 'cacao butter']); // true

// real world examples (Products searched on [USDA Food Composition Databases](https://ndb.nal.usda.gov/ndb/search/list))

const isVegan = require('is-vegan');

// MOSER ROTH, DARK CHOCOLATE
isVegan.isVeganIngredientList([
  'COCOA LIQUOR',
  ' SUGAR',
  ' COCOA BUTTER',
  ' ALKALIZED REDUCED FAT COCOA POWDER',
  ' SOY LECITHIN EMULSIFIER',
  ' GROUND VANILLA'
]); // returns true

// MISSION PIZZA CO., THIN CRUST PIZZA, COMBINATION
isVegan.isVeganIngredientList([
  'WATER',
  ' WHEAT FLOUR',
  ' PASTEURIZED MILK',
  ' PORK',
  ' TOMATOES',
  ' LIQUID & HYDROGENATED SOYBEAN OIL',
  ' CONTAINS 2% OR LESS OF THE FOLLOWING: PALM OIL',
  ' YEAST',
  ' SALT',
  ' MECHANICALLY SEPARATED CHICKEN',
  ' CORN MEAL',
  ' DEHYDRATED POTATOES',
  ' SUGAR',
  ' SPICES & SPICE EXTRACTIVES (INCLUDING PAPRIKA)',
  ' BEEF',
  ' CHEESE CULTURES',
  ' WHEAT GLUTEN',
  ' CULTURED WHEY',
  ' WHEY',
  ' ENZYMES',
  ' SODIUM ASCORBATE',
  ' VINEGAR',
  ' NATURAL & ARTIFICIAL FLAVOR',
  ' DEXTROSE',
  ' LACTIC ACID STARTER CULTURE',
  ' OLEORESIN OF PAPRIKA',
  ' LECITHIN',
  ' SODIUM NITRITE',
  ' CORN STARCH',
  ' MONOCALCIUM PHOSPHATE',
  ' SODIUM ACID PYROPHOSPHATE',
  ' SODIUM BICARBONATE',
  ' PROCESSING AIDS',
  ' CITRIC ACID',
  ' BETA CAROTENE',
  ' DIMETHYLPOLYSILOXANE',
  ' SOY LECITHIN',
  ' TBHQ',
  ' ONION POWDER',
  ' GRALIC POWDER',
  ' BHA',
  ' BHT',
  ' SOYBEAN OIL (PROCESSING AID)',
  ' ASCORBIC ACID',
  ' FERROUS SULFATE',
  ' FOLIC ACID',
  ' NIACIN',
  ' RIBOFLAVIN',
  ' THIAMINE MONONITRATE'
]); // returns false
```

## TODO

* add tests
* extend list

## Authors

* Hamed Montazeri
* Meike Rittmeier
