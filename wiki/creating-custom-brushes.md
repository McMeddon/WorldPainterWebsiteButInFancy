---
coverY: 0
---

# Creating Custom Brushes

## Custom Brushes

WorldPainter allows you to use custom brushes, enabling you to quickly create original and/or realistic terrain in all kinds of ways. A custom brush is simply a grey scale image, placed in the custom brushes folder. You can either create it yourself using a paint program such as [​GIMP](http://www.gimp.org) or [​Paint.NET](http://www.getpaint.net), or you can use custom brush or height map images taken from the Internet. Height maps of mountains, for instance, make good custom brushes.

For good results, there are some guidelines you should follow for creating or adapting the image:

* It should be square.
* It should have a decent size, otherwise WorldPainter will have to blow it up too much and it won't look good. For best results the size along each edge should be an odd number. 301 by 301 pixels is a good size. The maximum brush radius is 300, so making the image larger than 601 by 601 is not useful.
* It should be 8-bit grey scale.
* It should be white on black, meaning that white means maximum effect and black means no effect. It may have a transparent background, but it should still be white on transparent. If you have an image you want to use but it is black on white or black on transparent you should invert it using a paint program.
* The supported file formats depend on the Java runtime, so they may vary. PNG _should_ always be supported though, and is probably the best choice. JPEG will probably also work, but is not recommended, as it is a lossy format and as such may generate artefacts.
* Make sure that it fades to black all around the edges, or you will get ugly sheer cliffs around the edge when you use it to raise the terrain.

### Installing

To install the custom brush, move it to the custom brushes folder, which you can open from inside WorldPainter by selecting _Tools -> Open custom brushes folder_ in the menu. You will have to restart WorldPainter for it to show up. Once you have restarted WorldPainter, the new brush will appear as an extra button on the Brush panel, and you can use it just like any other brush.

**Note**: you can organise the custom brushes into separate subdirectories inside the brushes folder, which will show up as separate palettes in WorldPainter. This is especially convenient if you have many custom brushes, to prevent the palette from becoming so large that it doesn't fit on the screen.

### Creating Custom Brushes with WorldPainter

It is possible to create custom brushes using only WorldPainter itself, by painting a shape and exporting the map as a height map. Check out the following tutorial by Lentebriesje for details: [​http://www.youtube.com/watch?v=YwFK7MvsUss](http://www.youtube.com/watch?v=YwFK7MvsUss)

### Templates

It's easy enough to create an image yourself following the guidelines above, but to make it even easier here are a few templates you can use:

[​Small](http://www.worldpainter.net/images/custom\_brush\_template\_small.png) (151x151 pixels)

[​Medium](http://www.worldpainter.net/images/custom\_brush\_template\_medium.png) (301x301 pixels)

[​Large](http://www.worldpainter.net/images/custom\_brush\_template\_large.png) (601x601 pixels)

### Contributed Brushes

Here are various brushes created by WorldPainter users for you to use in WorldPainter:

[​Ecfio - 25 World Painter Custom Brushes](http://www.planetminecraft.com/project/ecfio---25-worldpainter-custom-brushes---by-tylertimoj/#comments) - by TylerTimoJ
