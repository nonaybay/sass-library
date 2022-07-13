
# function: scale

based on built-in function of sass: `color.scale()`
fluid increase or decrease any value in range of minimum ~ maximum

## Arguments
`$v: Initial value`
`$w: Weight to increase/decrease value`
`$n: Minimum value available`
`$x: Maximum value available`
`$i: Interval`
`$s: Scaler`

## Function
```
@function scale($v, $w, $n, $x) {
  @if ($w > 0) {
    $i: ($x - $v);
    $s: math.div(($w * $i), 100);
    $v: ($v + $s);
  } @else if ($w < 0) {
    $i: ($v - $n);
    $w: math.abs($w);
    $s: math.div(($w * $i), 100);
    $v: ($v - $s);
  } @else {
    $v: $v;
  }

  @return $v;
}
```
