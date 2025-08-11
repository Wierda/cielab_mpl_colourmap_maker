# CIE colourmaps for matplotlib

### Requirements
- `matplotlib`
- `numpy`
- `opencv`

### Usage
Import the `luv_colour_map` and/or `lch_colour_map` functions into your script. Both require a list of colours in the RGB format (normalised to 1) and a granularity in the form of `N_bins`, so e.g.
```
rgb_list = [(1, 0, 0), (0, 1, 0)]
colour_map = luv_colour_map(rgb_list, N_bins = 256)
```
The resulting colourmap can be used just like any other matplotlib colourmap. 

The difference between the two functions is that `luv_colour_map` does the colour interpolations linearly in CIELuv space, while `lch_colour_map` does them linearly in CIELCh_uv i.e. cylindrically in CIELuv. Additionally, `luv_colour_map` does some logic to make sure that the midpoint of the colourmap lies close to the perceived midpoint between the two colours (I think, it's been a few years since I made this). This makes `luv_colour_map` especially nice for fractions or for maps that need to centre at 0.
