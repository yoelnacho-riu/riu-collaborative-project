#### Icon example

```sh
$sizes: (
  sm: 40px,
  md: 50px,
  lg: 80px
);

@each $i, $size in $sizes {
  .icon-#{$i} {
    font-size: $size;
    height: $size;
    width: $size;
  }
}
```

#### theme

```sh
@forward 'base';
@forward 'utilities';

@use 'settings' as *;
@use 'tools' as *;

//Example: theme code
#{$token-prefix-class}-theme {
  background-color: adjust-color($token-color-black, $lightness: 20%, $alpha: -1);

  @include iota-breakpoint(xs) {
    background-color: adjust-color($token-color-black, $lightness: 20%, $alpha: -0.75);
  }
}
```

#### ts

```sh
import { Attribute } from '@angular/core';
...
constructor(@Attribute('ui-color') public uiColor?: string) {}
```
