---
description: Troubleshooting WorldPainter
coverY: 0
---

# 🤷♂ Troubleshooting

## Troubleshooting

This is the generic troubleshooting page. Don't forget to also check the troubleshooting page specific to your operating system:

{% content-ref url="troubleshooting-worldpainter-on-windows.md" %}
[troubleshooting-worldpainter-on-windows.md](troubleshooting-worldpainter-on-windows.md)
{% endcontent-ref %}

{% content-ref url="troubleshooting-worldpainter-on-mac-os-x.md" %}
[troubleshooting-worldpainter-on-mac-os-x.md](troubleshooting-worldpainter-on-mac-os-x.md)
{% endcontent-ref %}

{% content-ref url="troubleshooting-worldpainter-on-linux.md" %}
[troubleshooting-worldpainter-on-linux.md](troubleshooting-worldpainter-on-linux.md)
{% endcontent-ref %}





### WorldPainter won't start or isn't usable any more after a change

If you made a change (such as installing custom brushes or a plugin, or changing a preference) and now WorldPainter won't start any more, or isn't usable any more, try using [WorldPainter Safe Mode](https://www.worldpainter.net/trac/wiki/SafeMode). It will allow WorldPainter to start again, allowing you to undo the change you made, or confirm that the change was what caused the problem so you know to undo it.



### WorldPainter hangs during Export while using a lot of CPU and/or harddisk resources

If the Export appears to hang and WorldPainter is using a lot of CPU and/or the harddisk is continually being used then it may be that WorldPainter is trying to use too much memory, a condition called _thrashing_. See the [Thrashing](https://www.worldpainter.net/trac/wiki/Thrashing) page for instructions for fixing it.



### WorldPainter lags badly when I use an overlay image

This is a known problem in WorldPainter which some people experience, for as yet unknown reasons having to do with the image size and type. Try experimenting with different Overlay Scaling and Painting settings on the Performance tab of the Preferences screen.



### The brush is displayed off centre and it leaves a trail of garbage

This is a known problem in JIDE, the external library which we use for the docks. While we hunt for a permanent solution you can fix the problem whenever it occurs by resizing the WorldPainter window, or resizing the dock on the left of the WorldPainter window (by dragging the right edge of it).



### My virus scanner says there is a virus, trojan or other malware in WorldPainter

It is a false positive. There is no virus, trojan or other malware in WorldPainter. If your virus scanner says that there is, please report it to the makers as a false positive, and then use your virus scanner's "unquarantine" or equivalent functionality, or temporarily disable it, to be able to install and use WorldPainter. See the [FalsePositives](https://www.worldpainter.net/trac/wiki/FalsePositives) page for more information, including why you should upgrade to a better virus scanner.



### When I import a height map, or add a custom brush, the height mapping is not linear

If you import a height map, or add a custom brush, with a linear gradient in it, but in WorldPainter the gradient becomes curved instead, this may be caused by the image file having an alpha channel. The image should be 8-bit or 16-bit grey scale with _no_ alpha channel for optimum results. Try removing the alpha channel with an image editor such as [​GIMP](http://www.gimp.org) or [​paint.net](http://www.getpaint.net).



### The water is uneven or there are square patches of water on the world

There are various ways this could have happened, for instance:

* There used to be a bug in WorldPainter which could cause patches of water to remain behind if you cancelled a Flood operation. These patches would only be visible after saving and loading the world. The bug has been fixed, but if this happened to your world in the past the water patches might still be there.
* You can get standing columns or walls of water if you flood a valley, and then expand the valley by lowering the land around the edge without re-flooding the lake. When you expand a flooded valley, make sure to re-flood the lake by right-clicking on the water once with the Flood tool, and then left-clicking.
* Another way to get discrepancies in water height is by using the Sponge tool to reset the water level, and not finishing the entire area. When using the Sponge tool to reset the water level (by right-clicking), be careful to apply it to the entire body of water.

Regardless of how it happened, there are a few ways in which you can fix it:

* You can reset the water on the entire map using the "reset all water or lava" operation of the Global Operations tool (Ctrl+G or the globe icon on the Tools panel). This will reset the fluid level and type on the entire map to whatever you originally specified on the New World screen. The downside is of course that any valleys you dried will be refilled and lakes at other than default elevations will be removed or changed.
  * If you want to flood to a different level you can change the default water level like this, prior to resetting the water: Dimension Properties (Ctrl+P, toolbar button or Edit menu) -> Default Terrain tab -> check "beaches around water level" if it is unchecked -> change the water level -> uncheck "beaches around water level" if it was previously unchecked -> OK.
* Another technique for easily fixing a large body of water is to right-click with the Flood tool on an area of the water that is at the correct height (this will lower any water which was at a higher level), and then left-click to raise it back to the desired height (this will raise any water which was at a lower level).
* For more manual control you can use the Sponge tool. Left clicking completely removes water and lava. Right-clicking resets the water level to the default. See above for how to change the default water level.



### I get chunk errors / missing chunks / weird square patches with water or different landscape after exporting the world

This is probably for one of two reasons:

* You Exported a world you previously Imported from an existing map, instead of Merging it with the map from which you imported it.
* You made changes to chunks that were marked read-only (with a black cross across them) and neglected to remove the read-only layer (by right-clicking with the Read-only button selected) from those chunks.



### WorldPainter runs out of memory

* First, reconsider whether you really need to create a world of the size you're trying to create. Focus on quality, not quantity, especially for adventure maps. A large map will take far longer to make, and many Minecraft hosters won't allow maps larger than 5000 blocks squared. Server maps can generally support hundreds of players with just a few thousand blocks squared.
* Windows only: 64-bit WorldPainter can use much more memory than 32-bit WorldPainter. If you have 64-bit hardware, make sure to use the 64-bit version of Windows, Java and WorldPainter. If the installer tells you it can't find a Java VM, you may have to install 64-bit Java first, which you can get [here](https://www.worldpainter.net/links/jre-win-64) (pick the file ending in `.exe`).
* If you installed WorldPainter using an installer, it is already using the maximum recommended amount of memory (unless you are on Windows and are using the 32-bit version, see above). Install more memory (and reinstall WorldPainter, so that it will use it).
* If you installed WorldPainter from an archive, you can manually increase the amount of memory allocated to it by editing the `worldpainter.vmoptions` file (Windows or Linux) or `vmoptions.txt` file (Mac OS X). See the [MoreMemory](https://www.worldpainter.net/trac/wiki/MoreMemory) page for details on how to do that.



### There is water underneath all of my land

If there is ocean underneath your land after Exporting your world and opening it in Minecraft, you probably exported it in the wrong format with Populate enabled. If you Export the world in 1.12 format, and you used the Populate layer or you enabled "allow Minecraft to populate the entire terrain", and then you open the map in Minecraft 1.13 or later, then Minecraft will regenerate (part of) all the chunks marked as "to populate".

To prevent this, Export the world in Minecraft 1.15+ format. Unfortunately Minecraft 1.13 and later don't support populating chunks, so you will have to use WorldPainter layers to generate all the structures you need, including vegetation, trees, lakes, buildings, etc..

[Last modified](https://www.worldpainter.net/trac/wiki/Troubleshooting?action=diff\&version=8) [11 months ago](https://www.worldpainter.net/trac/timeline?from=2021-04-18T20%3A49%3A57%2B02%3A00\&precision=second)\
