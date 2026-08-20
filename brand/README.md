# Brand assets

Source of truth is [`cla-logo.svg`](cla-logo.svg). The PNGs are generated from
it — regenerate rather than editing them by hand.

| File | Size | Use |
| --- | --- | --- |
| `cla-logo.svg` | 504×465 | Source. Navy `#101e41`, teal `#209a8f` |
| `org-avatar-500.png` | 500×500 | GitHub organization avatar |
| `app-logo-512.png` | 512×512 | GitHub App logo |
| `app-logo-200.png` | 200×200 | GitHub App logo, if 512 is rejected |
| `logo-1024.png` | 1024×1024 | Master raster, docs and README |
| `social-preview-460.png` | 460×460 | Repository social preview |
| `logo-1024-transparent.png` | 1024×1024 | Transparent, for placing on your own background |

## Why the PNGs look the way they do

**Padded, never stretched.** The source is 504×465. GitHub crops avatars
square, so the artwork is centred on a square canvas rather than scaled to fit —
stretching would turn the `C` arc into an ellipse.

**Logo occupies 72% of the canvas.** GitHub renders avatars as circles in some
places (commit authorship, comment threads). At full bleed the `A` and the outer
arc clip at the circle's edge.

**White background, alpha flattened.** The navy is nearly invisible against a
dark background, so the white-backed variants are the safe default everywhere.
Flattening avoids grey fringing when GitHub composites over a non-white surface.

Use `logo-1024-transparent.png` when you control the background. Note the navy
needs a light backdrop; on a dark one, recolour `#101e41` toward `#f5f7fa`
first.

## Regenerating

Requires ImageMagick.

```sh
gen() {  # size, inner-ratio, output
  inner=$(python3 -c "print(int($1*$2))")
  convert -background none -density 600 cla-logo.svg -resize ${inner}x${inner} \
    -gravity center -background white -extent $1x$1 \
    -alpha remove -alpha off -strip "$3"
}

gen 500  0.72 org-avatar-500.png
gen 512  0.72 app-logo-512.png
gen 200  0.72 app-logo-200.png
gen 1024 0.72 logo-1024.png
gen 460  0.80 social-preview-460.png

convert -background none -density 600 cla-logo.svg -resize 737x737 \
  -gravity center -background none -extent 1024x1024 -strip logo-1024-transparent.png
```

Keep every file under GitHub's 1 MB upload limit. The current set peaks at
about 83 KB.

## Where these get uploaded

Both are manual, and neither is stored in a repository:

- Organization avatar — Organization settings → Profile
- GitHub App logo — Settings → Developer settings → GitHub Apps
