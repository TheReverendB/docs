# Overlays

You can also add overlays on the map.  These include Arrows and Spell overlays.

## Arrow overlays

Arrows can now be drawn as overlays on the map. They support a start point, an end point and a color. Arrows are initiated with a `*a`. The formula is `*a[<color>]<start point><end point>`. The most common use case for arrows is to show movement for a token.

**Example**

```
https://otfbm.io/*aRa1g4/g4r/
```

![](https://otfbm.io/*aRa1g4/g4r/)

## Spell overlays

To draw a spell overlay, use the `*` character then the following shape codes: `c` circle, `l` line, `s` square, `t` cone. See below for parameters.

## Overlay types with examples

```
https://otfbm.io/*c20rd5
```

![](https://otfbm.io/*c20rd5)

`*c` circle `20` diameter `r` _colour_ `d5` center co-ordinate  

Alternatively use `*ct` to anchor the circle from the top left.

```
https://otfbm.io/*t50ba5e5
```

![](https://otfbm.io/*t50ba5e5)

`*t` cone `50` length `b` _colour_ `a5` start co-ordinate `e5` direction co-ordinate

```
https://otfbm.io/*l30,5ga1b2
```

![](https://otfbm.io/*l30,5ga1b2)

`*l` line `30` length `,5` _width_ `g` _colour_ `a1` start co-ordinate `b2` direction co-ordinate

```
https://otfbm.io/*s30ca1b2
```

![](https://otfbm.io/*s30ca1b2)

`*s` square `30` size `c` _colour_ `a1` start co-ordinate `b2` direction co-ordinate  

Alternatively use `*st` to anchor the square at the top left. (Or don't specify the direction co-ordinate.)

```
https://otfbm.io/*a10pD3E5
```

![](https://otfbm.io/*a10pD3E5)

`*a` arrow `10` size `p` _colour_ `d3` start co-ordinate `e5` direction co-ordinate  
