# SCSS

## Variable

```scss
$color: #f00;

.class {
  color: $color;
}
```

## Class

```scss
%my-class {
  width: 100px;
}

.class {
  @extend %my-class;
}
```

## Mixin

```scss
@mixin my-class($color, $size) {
  color: $color;
  font-size: $size;
}

.class {
  @include my-class(#fff, 16px);
}
```
