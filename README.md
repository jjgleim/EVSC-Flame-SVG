# EVSC TRMNL Flame SVG

## How to Create and Use the Flame in TRMNL

1. Export a PNG of the flame from Adobe Illustrator that is 400 x 400px.
2. Upload PNG to <a href="https://pngtosvg.com/" target="_blank">https://pngtosvg.com/</a> and download the SVG.
3. Upload SVG to GitHub.
4. Click on the file to preview it.
5. **Press `y` on your keyboard.** The URL changes from `.../blob/main/...` to
   `.../blob/<40-character commit SHA>/...` — this pins the link to this exact
   version of the file. See "Why pinning matters" below.
6. Click the RAW button in the toolbar at the top-right of the screen.
7. Copy the SVG URL from address bar.
8. Paste SVG URL into code.

## Why pinning matters

The two URL shapes look nearly identical but behave very differently:

```
Tracks main — changes the instant you edit the file:
https://raw.githubusercontent.com/jjgleim/EVSC-Flame-SVG/refs/heads/main/flame.svg

Pinned to a commit — frozen forever:
https://raw.githubusercontent.com/jjgleim/EVSC-Flame-SVG/8e31dcf.../flame.svg
```

This repo is shared across multiple projects. That is the point — but it also
means a single edit here propagates to every project at once, with no deploy
step and no warning.

On an e-ink door sign that is a real hazard. The display renders on a limited
ink set, so a flame that looks fine on a monitor can quantize badly on the
panel. If the logo is tracking `main`, the sign changes on its own the next time
it refreshes, and nothing in the *consuming* project's git history will explain
why.

**Rule of thumb:** track `main` while you are still iterating on a project, pin
before you call it done. Pinning does not cut the project off from updates — it
makes taking an update a deliberate act: swap the SHA when you want the new
flame, and the change shows up in that project's commit history where it
belongs.

If you skip step 5 and need to pin later: open the file, click **History**, then
the `<>` icon ("Browse the repository at this point in the history") beside the
commit you want. That view is SHA-pinned, so RAW from there gives a pinned URL.

## Variants

| File | Use on |
| --- | --- |
| `evsc-flame-red-color.svg` | Color displays (Seeed Studio E1002, 6-ink) |
| `evsc-flame-grayscale-bw-v2.svg` | 1-bit black & white displays (TRMNL OG) |

## Related Resources

- [TRMNL — Creating Inline Images for Plugins](https://help.trmnl.com/en/articles/12391781-creating-inline-images-for-plugins)
- [PNGtoSVG.com](https://pngtosvg.com/)
