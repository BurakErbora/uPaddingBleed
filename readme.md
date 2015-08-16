Adds bleed to padded unity tilesheets. Unity's texture packer adds padding to textures when packing but leaves this space black and transparent which makes mipmapping the atlas or even using bilinear or trilinear filterint impossible. This script can either repeat each texture in the padding (for tilesheets of repeating tiles) or stretch the edge pixels to fill the padding (for standalone tiles).

##Usage

```
//Generate your atlas as you would normally
Rect[] rects = atlas.PackTextures(atlasTextures, 32, 8192, false);
//Call bleed edges to fill the padding
uPaddingBleed.BleedEdges(atlas, 32, rects, repeatingTextures: true);
```

Pass it the texture, the padding amount, some or all of the rects to apply padding fill to and lastly whether or not to repeat the texture or stretch the edges.