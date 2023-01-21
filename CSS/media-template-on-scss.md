## scss에서 media 쿼리 세팅

```scss
/*반응형 화면 크기*/
$mobile: 768px;
$tablet: 1024px;

@mixin mobile {
  @media (max-width: #{$mobile - 1px}) {
    @content;
  }
}

@mixin tablet {
  @media (min-width: #{$mobile}) and (max-width: #{$tablet - 1px}) {
    @content;
  }
}

@mixin desktop {
  @media (min-width: #{$tablet}) {
    @content;
  }
}
```

사용

```scss
@include mobile {
  .Close {
    display: none;
  }
  .Open,
  .Open > div {
    display: flex;
    flex-direction: column;
  }
}
```
