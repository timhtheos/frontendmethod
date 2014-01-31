Property order:
Generally i put all mixins at the top, font things together, then margins & padding together, etc.

.label__product {
  @include font-size(18px);
  @include font($dark-green, $normal, $fjalla, $uppercase);
  padding: 1em 0 0.25em 0;
  margin-bottom: 0.938em;
  clear: both;
}
