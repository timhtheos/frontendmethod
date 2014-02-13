# Formatting Guidelines
At the base level of formatting, all rule declarations should be constructed in the following manner:

```css
selector {
  property: value;
}
```

## Whitespace
### Blank lines
 * In general, do NOT separate each ruleset by a blank line.
 * If a ruleset has a proceeding Doxygen-style or single-line-style comment that describes it, place a blank line before the comment.
 * If two rulesets have no interleaving blank line, they must be logically related. If they are not logically related to each other, add a blank line and a comment describing the second ruleset.

```sass
// Bipeds have hands
.person {
  display: inline-block;
}
.person__hand {
  positoin: absolute;
}
.person__hand--left {
  right: 0;
  left: auto;
}

// Quadrapeds have paws
.dog {
  display: cute;
}
.dog__paw {
  background-color: brown;
  position: absolute;
  bottom: 0;
}
.dog__paw--right {
  background-color: #fefcfd;
  right: auto;
  left: 0;
}
```

## Format
### Rulesets
 * Use one selector per line when a ruleset has a group of selectors separated by commas.
 * The opening brace ``` { ``` of a ruleset's declaration block should be on the same line as the selector (or the same line as the last selector, in a group of selectors.) The opening brace should include a single space before it.
 * Place the closing brace ``` } ``` of a ruleset in the same column as the first character in the selector of the ruleset.
 * Include one declaration per line in a declaration block.
 * Each declaration should be indented one level (two spaces) relative to its selector.

```sass
.selector-alpha,
.selector-beta {
  counter-reset: section;
  text-transform: small-caps;
}
```

### Properties
 * In a declaration, the property name should be immediately followed by a colon, then a single space, and then the property's value.
 * Include a semi-colon at the end of all declarations, including the last declaration in a declaration block.
 * When hex values are used for colors, use lowercase and, if possible, the shorthand syntax. Colors may be expressed with any valid CSS value, such as hex value, color keyword, rgb() or rgba(). Note that IE8 does not support all color syntaxes and will require a fallback value.
 * For property values that require quotes, use double quotes instead of single quotes.  For items inside quotes as property values, shall be separeted a single space.
 * Quote attribute values in selectors.
 * Where allowed, avoid specifying units for zero-values.
 * Include a space after each comma in comma-separated property or function values.
 
#### Property Order:
1. SASS includes
2. Positioning properties
  * position
  * float
  * clear
  * top
  * right
  * bottom
  * left
  * direction
  * z-index
3. Box model properties
  * display
  * [(max|min)-]height
  * [(max|min)-]width
  * margin
  * padding
  * border
  * box-sizing
  * various longhand formats (margin-top, etc.)
4. Visual style properties
  * background 
  * color
  * font
  * text
5. Other declarations

Mixins should be included first because of the cascading order - it should be easy to "reset" any properties defined in the included mixin.  There shall be a single line space between the mixins and the other properties defined.

```sass
.label__product {
  @include font-size(18px);
  @include font($dark-green, $normal, $fjalla, $uppercase);
  
  padding: 1em 0 0.25em 0;
  margin-bottom: 0.938em;
  clear: both;
}
```

#### Exceptions & Deviations
Large blocks of single declarations can use a slightly different, single-line format. In this case, a space should be included after the opening brace and before the closing brace.

```sass
.selector-1 { width: 10%; }
.selector-2 { width: 20%; }
.selector-3 { width: 30%; }
```

Long, comma-separated property values, such as collections of gradients or shadows, can be arranged across multiple lines in an effort to improve readability and produce more useful diffs.

```sass
.selector {
  background-image:
    linear-gradient(#fff, #ccc),
    linear-gradient(#f3c, #4ec);
  box-shadow:
    1px 1px 1px #000,
    2px 2px 1px 1px #ccc inset;
}
```
