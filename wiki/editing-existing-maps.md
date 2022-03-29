---
coverY: 0
---

# ✏ Editing Existing Maps

### How do I edit existing Minecraft maps?

WorldPainter is a map generator, not an editor! The basic idea is to use it for generating new maps which you then edit with other tools such as creative mode, [​WorldEdit](https://dev.bukkit.org/projects/worldedit), [​VoxelSniper](https://dev.bukkit.org/bukkit-plugins/voxelsniper/) or [​MCEdit](https://www.mcedit.net).

Having said that, WorldPainter does have limited support for making changes to existing maps, using the Import and Merge operations. Import (Ctrl+I or File -> Import -> Existing Minecraft map...) will create a new WorldPainter world based on the landscape (terrain height and type and biome information, but no underground or above ground structures, trees, etc.) of an existing map. Merge (Ctrl+R or File -> Merge world...) will merge any changes you make back to the existing map.

**Important notes:**

* You have to use Merge (Ctrl+R), not Export, to save your changes back to the existing map!
* When Importing an existing map, any chunks containing man-made blocks will be marked read-only, visible by a black cross across them. This includes underground blocks from mines and strongholds. Chunks that are marked read-only are not merged during the Merge process. You can still make changes to them in the editor, but those changes won't be saved. This is to protect man made structures from the merge process, which can be destructive and mangle structures, especially if you changed the slope of the terrain. If you still want to make changes to those chunks (at your own risk), you can remove the read-only layer (like any other layer: select the Read-only button and right-click to remove it). Note that you can also _add_ the read-only layer to areas where you don't intend to make changes, which will speed up the merge process.
