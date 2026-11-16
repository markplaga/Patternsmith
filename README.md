# Patternsmith

A laser-cutter pattern maker that exports ready-to-cut SVGs. It's a sibling to [Boxsmith](https://github.com/markplaga/Boxsmith) and [Polysmith](https://github.com/markplaga/Polysmith).

**The rule it never breaks:** no two cuts ever touch. Every cut stays at least one *gap* away from every other cut and from the outline, so every bridge of material is at least that wide.

## Features

- **Piece outlines:** rectangle (rounded corners optional), circle, hexagon, octagon, triangle, pentagon, or pattern only.
- **Layouts:** square grid, offset (hex) grid, radial rings (mandala), sunflower spiral, random scatter, and cells (honeycomb, square tiles, triangles, organic Voronoi) with rounded corners.
- **Shapes:** circle, hexagon, square, triangle, diamond, octagon, 5- and 6-point stars, heart, teardrop, leaf, slot, cross, crescent. Rotation can be fixed, pointing outward, alternating or random.
- **Size variation:** linear gradient, radial, waves, organic noise, random.
- **Enlarge to fill:** elements grow into the free space, and grids stretch edge to edge, without ever closing a gap.
- **Kerf awareness:** shows the bridge width left after the kerf and warns when bridges get fragile.
- **Stats:** shape count, cut length and estimated cut time.
- **26 presets.**

## How spacing is guaranteed

- **Shapes** are checked by the circle they fit inside, so any rotation is safe.
- **Cells** are Voronoi cells clipped by half-planes moved inward by half the gap, so neighbours are exactly one gap apart.
- **The outline** is approximated by an inscribed convex polygon, and everything is kept at least the margin inside it. The margin is never smaller than the gap.

## Output

- Units are millimetres (`width="…mm"`, `viewBox` in mm).
- Red (`#ff0000`) is the inner cuts. Cut these first.
- Blue (`#0000ff`) is the outline. Cut this last.
- Strokes are 0.1 mm hairlines with no fill.

## Use

Open `index.html` in a browser. It's a single self-contained file with no dependencies.
