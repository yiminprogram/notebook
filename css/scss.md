# SCSS

## Variable

```scss
$color: #f00;

.class {
  color: $color;
}
```

## Extend

```scss
.my-class {
  width: 100px;
}

.class {
  @extend .my-class;
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

### mixin default value

```scss
@mixin my-class($color: #f00) {
  color: $color;
}

.class {
  @include my-class();
}
```

### mixin media query

```scss
@mixin pad {
  @media (max-width: 768) {
    @content;
  }
}

@mixin mobile {
  @media (max-width: 568px) {
    @content;
  }
}

.class {
  width: 500px;
  @include pad {
    width: 300px;
    font-size: 35px;
  }
}
```

## Function

```scss
@function myFontSize($pixel) {
  @return $pixel * 2;
}

.class {
  width: 300px;
  font-size: myFontSize(30); //return 60px;
}
```

## Emoji

```scss
content: '\u{1F600}';
```
