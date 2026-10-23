# topological-map-inf
Procedurally generated infinite topological map background
# Topographic Dream

A procedurally generated, infinitely scrolling topographic landscape for the browser.

Topographic Dream creates monochrome, map-inspired landscapes using mathematical terrain functions and SVG contour lines. It runs entirely in the browser, requires no external dependencies, and lets you explore continuously scrolling terrain generated from a seed.

Inspired by the concept of [Shan Shui](https://github.com/LingDong-/shan-shui-inf), an infinitely scrolling, procedurally generated landscape project, Topographic Dream explores a more minimal, cartographic aesthetic.

## Features

- **Infinite horizontal scrolling** — a seamless, repeating landscape tile creates a continuous visual experience.
- **Procedural terrain generation** — overlapping mathematical elevation fields produce hills, valleys, ridges, and irregular terrain.
- **Seed-based generation** — use a seed to reproduce a particular landscape.
- **Monochrome aesthetics** — fine charcoal contour lines on a warm, off-white background.
- **Adjustable scrolling speed** — speed up or slow down the animation while exploring.
- **SVG and PNG export** — save the generated landscape as a vector graphic or raster image.
- **Minimal interface** — full-screen visuals with unobtrusive controls and a translucent settings menu.
- **SVG element budget** — designed to keep the generated SVG structure within a limit of 200 elements.
- **Zero dependencies** — implemented with HTML, CSS, JavaScript, and browser-native SVG APIs.

## Getting Started

### Run locally

No installation, build tools, or package manager are required.

1. Download or clone this repository.
2. Open `index.html` in a modern web browser.
3. Explore the continuously scrolling landscape.

The application runs client-side and does not require a backend server.

## Controls

| Control | Function |
|---|---|
| `−` | Decrease scrolling speed |
| `+` | Increase scrolling speed |
| `☰` | Open or close the settings menu |
| Generation seed | Enter a seed for reproducible terrain |
| Regenerate | Generate the terrain associated with the current seed |
| New seed | Create a new seed and generate another landscape |
| Export SVG | Save the current landscape as an SVG file |
| Export PNG | Export a rasterized PNG image |

## How It Works

### 1. Seeded randomness

A deterministic pseudorandom number generator converts the input seed into repeatable values. These values determine the placement, dimensions, and amplitudes of the terrain features.

Using the same seed reproduces the same procedural terrain.

### 2. Procedural elevation field

The generator combines multiple Gaussian-shaped elevation features with periodic sinusoidal functions. Positive and negative contributions create elevated regions, depressions, and ridges.

The terrain is evaluated across a grid of sample points to produce an elevation field.

### 3. Contour extraction

Marching Squares examines each grid cell and locates the intersections between cell edges and selected elevation thresholds. These intersections are connected into contour segments.

Multiple segments are combined into SVG paths, reducing the number of SVG elements needed to render the landscape.

### 4. Seamless horizontal tiling

The terrain uses horizontally periodic elevation functions. This allows the right edge of a tile to connect with its left edge.

The tile is repeated using an SVG pattern and translated continuously across the viewport. When one tile passes out of view, the next identical tile occupies its place.

### 5. Browser-native rendering

The landscape is rendered as SVG paths, keeping the contours sharp at different display sizes. CSS provides the full-screen layout and translucent controls, while JavaScript handles generation, animation, and exports.

## Technology Stack

- **HTML5** — application structure
- **CSS3** — full-screen presentation, responsive layout, and interface styling
- **Vanilla JavaScript** — seeded procedural generation and animation
- **SVG** — vector terrain rendering and seamless pattern repetition
- **Canvas API** — SVG-to-PNG export

No frameworks, external assets, or third-party libraries are required.

## Design Goals

Topographic Dream focuses on the visual language of topographic maps rather than traditional landscape illustration.

Its design emphasizes:

- Sparse, restrained monochrome styling
- Organic terrain generated from mathematical functions
- Dense contour patterns with varying line weights
- Continuous movement without visible horizontal seams
- Reproducible output through deterministic seeds
- A compact, self-contained implementation

## Current Limitations

- **Repeating terrain:** the landscape loops seamlessly but eventually repeats the same tile; it does not generate an indefinitely evolving world.
- **Procedural abstraction:** the terrain is a mathematical elevation field, not a physically accurate geographical model.
- **SVG complexity:** the element limit controls the number of SVG nodes, not the number of path segments or the total file size.
- **Resolution and performance:** grid density and contour complexity affect generation time and rendering performance.

The application is currently self-contained in one HTML file, including its styles, procedural generation logic, animation, controls, and export functionality.

## Inspiration

Topographic Dream draws conceptual inspiration from [LingDong-'s Shan Shui Infinite](https://github.com/LingDong-/shan-shui-inf), which explores procedural landscape generation and infinitely scrolling SVG artwork.
This project takes a different visual direction, focusing on topographic contours, minimal monochrome composition, and a compact browser-based generator.


