# Arena Assets

Original artwork created for this exercise, not copied from Bomberman. These assets may be used, modified, and redistributed for coding exercises and candidate submissions without attribution.

| Asset                          | Purpose                                            | Background  |
| ------------------------------ | -------------------------------------------------- | ----------- |
| [floor.svg](floor.svg)         | Walkable tile                                      | Opaque      |
| [wall.svg](wall.svg)           | Boundary and internal wall                         | Opaque      |
| [player.svg](player.svg)       | Cyan player character                              | Transparent |
| [enemy.svg](enemy.svg)         | Red enemy robot                                    | Transparent |
| [bomb.svg](bomb.svg)           | Placed bomb before detonation (optional extension) | Transparent |
| [explosion.svg](explosion.svg) | Detonating bomb / blast tile (optional extension)  | Transparent |

All six images are **64 x 64 pixels**, with a `32 x 32` viewBox and crisp pixel-art edges. They are standalone SVG images without scripts, fonts, or external dependencies. No sprite-sheet slicing is needed. Floor, wall, player, and enemy are the core set; bomb and explosion are for the optional bomb extension.

## Use in Your Project

Place the SVG files in your framework's public assets directory, for example `public/assets`. They will typically be available at `/assets/floor.svg`, `/assets/wall.svg`, `/assets/player.svg`, and `/assets/enemy.svg`, with `/assets/bomb.svg` and `/assets/explosion.svg` for the optional extension. Adjust these URLs for your project's base path if needed.

Use the files as image URLs with browser `Image` objects for the promise-loading task. Do not inline or import them as SVG components, since that would bypass image loading.

For DOM rendering, place the player or enemy image over a floor image. For Canvas, draw the floor first and then the character at the same tile coordinates. Render all images at the same size; 64 pixels or another integer multiple of 32 keeps the artwork sharp. With Canvas, disable image smoothing if scaling.

For the optional bomb extension, place the bomb over a floor tile. On detonation, replace it with the explosion image and draw that image on each affected walkable tile. The explosion is a single static blast sprite, not an animation; blast range, wall blocking, duration, and removal are game logic for the candidate to implement.
