---
coverY: 0
---

# 🌳 Adding Custom Objects

## Custom Objects

WorldPainter allows you to include arbitrary, custom made objects in the world. You can use this to, for instance, create forests with tree types or other vegetation that WorldPainter (or Minecraft) doesn't support, or sprinkle buildings or artefacts around. Since these "objects" can also consist of water and/or empty space, and can be below ground, you can use them in various advanced techniques to create rivers and underground caverns or tunnels with more control than WorldPainter allows.

WorldPainter currently supports four custom object formats:

* The bo2 and bo3 formats (as used by the [​Terrain Control](https://minecraft.curseforge.com/projects/terraincontrol) mod).
  * Note that the bo2 and bo3 support is limited; they can have various properties, but most of these are ignored by WorldPainter. In particular, WorldPainter does _not_ support groups or branches! The only properties which are supported are `spawnWater`, `spawnLava`, `needsFoundation` and `randomRotation`. For bo3 objects random blocks and tile entities _are_ supported.
* The schematic format (as used by [​MCEdit](https://www.mcedit.net)).
* The nbt format (as exported by Minecraft itself using [​Structure Blocks](https://minecraft.gamepedia.com/Structure\_Block))
  * **Please note:** to support .nbt files, WorldPainter needs access to a Minecraft version 1.10 or 1.12 installation at the default location
  * For nbt objects, entities and tile entities are not yet supported.

The way you use these objects is as follows:

1. Click on the + button on the Layers panel and choose "Add a custom object layer".
2. Add one or more .bo2, .bo3, .schematic or .nbt files to the list using the + button.
   * Note that if you want some objects to be more prevalent than others you can adjust the relative frequency of each object, after adding it to the list, by clicking the button in the Options column or double clicking on the row.
3. Type a name for the layer in the Name field. This name will be displayed on the button, so keep it short.
4. Choose a colour. This is the colour with which the layer will be displayed in the editor. Choose different colours for different layers or you won't be able to keep them apart.
5. Press OK and click on the new button on the Layers panel to begin painting with the layer.
   * Note that you can paint with different intensities just like with any other layers. The higher the intensity, the more dense the objects will be.
   * The objects will be randomly rotated and mirrored to add variety (although you can turn this off in the object options).

### Custom Object Sites

There are a few web sites where you can download collections of custom objects which you can use in WorldPainter:

[​Custom Tree Repository](http://www.planetminecraft.com/project/native-trees-of-europe-template-repository-1779952/) by Lentebriesje - a huge collection of ready to use tree objects

[​MassiveCraft](http://massivecraft.com/plugins/terraincontrol)
