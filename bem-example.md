# BEM - Block, Element, Modifier

```
.person
.person__hand
.person__hand--left
.person--female
.person--female__hand
```

##### Block
```
.sidebar {}
```

##### Element
```
.sidebar__menu {}
```

##### Modifier
```
.sidebar--forum {}
```

## Drupal example

`l-branding` and `l-region-branding` are blocks and the `l` says they are part of the layout.  `.tagline` is a block while `tagline--mobile` is a modifier.

##### tpl.php
```html+php
<div class="tagline">
  <?php print $site_slogan; ?>
</div>
<div class="l-branding">
  <div class="l-region-branding">
    <?php print render($page['branding']); ?>
    <div class="logo">
      <?php if ($logo): ?>
      <a href="<?php print $front_page; ?>" title="<?php print t('Home'); ?>" rel="home" class="site-logo"><img src="<?php   print $logo; ?>" alt="<?php print t('Home'); ?>" /></a>
      <?php endif; ?>
    </div>
    <div class="tagline--mobile">
      <?php print $site_slogan; ?>
    </div>
  </div>
</div>
```

##### layout.scss
```sass
.l-branding {
  @include breakpoint(30em) {
    text-align: center;
    clear: both;
  }
  @include breakpoint(40.375em) {
    @include grid-span(2, 1, 9);
  }
  @include breakpoint(50em){
    @include grid-span(2, 1, 12);
  }
  @include breakpoint(69em) {
    @include grid-span(2, 1, 16);
  }
}

.tagline {
  display: none;
  @include breakpoint(40.375em){
    @include grid-span(6, 3, 9);
    display: block;
  }
  @include breakpoint(50em){
    @include grid-span(8, 4, 12);
  }
  @include breakpoint(75em){
    @include grid-span(3, 3, 16);
  }
}

.tagline--mobile {
  @include breakpoint(40.375em){
    display: none;
  }
  @include breakpoint(50em){
  }
}
```

