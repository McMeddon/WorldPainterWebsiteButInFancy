---
description: Frequently Asked Questions / HOWTO
cover: ../.gitbook/assets/5k Minecraft Map - Itoro - By McMeddon (8).jpg
coverY: -42.290748898678416
---

# FAQ

### I'm having trouble installing WorldPainter. I get an error message while running WorldPainter, or WorldPainter won't start. How do I fix it?

Check the [Troubleshooting](https://www.worldpainter.net/trac/wiki/Troubleshooting) page for various problems you may encounter and their solutions or workarounds.

### How do I play the world? How do I put the map I made in Minecraft?

Press Ctrl+E (⌘+E on a Mac) or use the File -> Export -> Export as Minecraft map... menu item. It will export the world directly to your Minecraft saves directory, after which it will appear in Minecraft under Singleplayer.

### How do I edit existing Minecraft maps?

WorldPainter is a map generator, not an editor! The basic idea is to use it for generating new maps which you then edit with other tools such as creative mode, [​WorldEdit](https://dev.bukkit.org/projects/worldedit), [​VoxelSniper](https://dev.bukkit.org/bukkit-plugins/voxelsniper/) or [​MCEdit](https://www.mcedit.net).

Having said that, WorldPainter does have limited support for making changes to existing maps, using the Import and Merge operations. Import (Ctrl+I or File -> Import -> Existing Minecraft map...) will create a new WorldPainter world based on the landscape (terrain height and type and biome information, but no underground or above ground structures, trees, etc.) of an existing map. Merge (Ctrl+R or File -> Merge world...) will merge any changes you make back to the existing map.

**Important notes:**

* You have to use Merge (Ctrl+R), not Export, to save your changes back to the existing map!
* When Importing an existing map, any chunks containing man-made blocks will be marked read-only, visible by a black cross across them. This includes underground blocks from mines and strongholds. Chunks that are marked read-only are not merged during the Merge process. You can still make changes to them in the editor, but those changes won't be saved. This is to protect man made structures from the merge process, which can be destructive and mangle structures, especially if you changed the slope of the terrain. If you still want to make changes to those chunks (at your own risk), you can remove the read-only layer (like any other layer: select the Read-only button and right-click to remove it). Note that you can also _add_ the read-only layer to areas where you don't intend to make changes, which will speed up the merge process.

### Is Multiplayer supported? How do I put the map on a Minecraft server?

Yes, Multiplayer is supported. Multiplayer maps are exactly the same as Singleplayer maps. Just Export the world like normal. Then, if you run the Minecraft server on the same computer, just move or copy the generated map directory to your Minecraft server installation directory, edit the `level-name` property in the `server.properties` file to be the same name as the directory, and (re)start the server. If the server is on a different computer the steps are the same, but you will have to transfer the map to the server somehow, generally by zipping it and transferring it to the server using a program such as Filezilla. Those details are beyond the scope of this site though. Ask your server administrator for the best way to transfer maps to the server, or google the subject.

### How do I use the Caves/Tunnels layer?

Check out [this](https://www.worldpainter.net/trac/wiki/CavesAndTunnels) page for instructions on using the Caves/Tunnels custom layer.

### How do I make the borders of the map look nice and integrate well with the Minecraft landscape?

When you leave the WorldPainter-generated chunks, Minecraft will start generating land again, according to the seed you specified and its own algorithms. There is nothing WorldPainter can do to avoid that. If you don't take this into account, the edges or seams between your world and the Minecraft world may be very abrupt and ugly. There are several strategies for making the seams look good:

1. Make the edges of your world all water, and use the "ocean" Minecraft seed option (the default) on the New World screen. Make sure to use the default water level for your world (62) and make the water depth around the edges at least fifteen blocks so it will match the ocean floor better. This will embed your world into a huge ocean and since the seams are all water they will be almost unnoticeable. Note that this does mean that there will be no other continents anywhere nearby though!
2. Configure a border on the Export screen. Note that this doesn't get rid of the seams, it just moves them further away. Also note that if the edges of your world are land (instead of water), or if the water level of your map is different than the border level, there will still be an ugly edge between your land and the border.
3. Use the "bedrock wall" option on the Export screen to make it hard to leave your world. Note that it is still possible to leave it, since you can just build your way to the top of the wall and walk right over it. And of course it means an ugly wall all around your world. You can combine this option with a border, so that you at least can't see the wall from the shores of your world.
4. Use the Import/Merge functions to smooth the seams after the fact:
   * Export your world
   * Load it in Minecraft, and fly along all the edges, forcing Minecraft to generate all the chunks around the edges
   * Import the map into WorldPainter using Ctrl+I or File -> Import -> Existing Minecraft map...
   * Use the Smooth tool, terrain tools, and any other tool of your choice to merge and smooth the seams
   * Select the Read-only layer, select a large and solid brush and set the intensity to full, and paint the entire interior of the world with the Read-only layer. This will greatly speed up the merge process. Be careful not to mark any chunks near the seams read-only though, as your edits in those chunks would be lost
   * Merge the changes with the original map using Ctrl+R or File -> Merge World...
   * The downside of this is that changing the slope of the land will mess up any trees that were on it. You'll have to visit all the seams again in Minecraft to manually fix problems introduced by the merge

### How do I change the water level on an existing world or map?

The first step is to change the default water level setting by opening the Dimension Properties (Ctrl+P or Edit menu), going to the Theme tab and adjusting the number at the bottom of the screen. You may have to temporarily enable "beaches around water level" to be able to change the setting.

Then you have a choice. You can either reset the water level across the entire world in one go with the Global Operations tool , or you can adjust the water level manually using the Flood and/or Sponge tools.

To reset the water across the world in one go, open the Global Operations tool (Tools panel or Ctrl+G), select "reset all water or lava" and press Go. The advantage of this is that it's quick and thorough, and it also resets the groundwater level in dry areas, so that the water level remains correct even if you change the elevation of currently dry areas. The downside is that it will remove all lava, and bodies of water that were above sea level, and will flood valleys that are below sea level.

To do it manually, use the Flood tool to raise the level of bodies of water by left-clicking on them, or lower them by right-clicking on them. Be careful not to interrupt the flooding operation, that may cause tiles with incorrect water levels to be left behind. You can also use the Sponge tool: right-clicking with it will reset the water level to the default in the area covered by the brush. Left-clicking the Sponge tool removes the water (or lava) altogether.

### How do I control WorldPainter with the keyboard? What are the keyboard shortcuts?

There are keyboard shortcuts for many aspects of WorldPainter. Check the [KeyboardShortcuts](https://www.worldpainter.net/trac/wiki/KeyboardShortcuts) page for an overview.

### How do I add custom blocks from mods to the map?

WorldPainter supports custom mod blocks with non-standard ID's (even ID's between 255 and 4096). **Note:** for block ID's above 255 you have to enable "extended block IDs", either on the New World screen, or afterwards from the Edit menu.

We can't help you with which block ID's to use, you'll have to find that out from the mod website or ask the authors or other users. Once you know the block ID to use there are four ways of adding custom blocks to the world:

1. Use one of the Custom terrain types (one of the buttons with a question mark on them). This will set the surface layer of the world to the custom block wherever you paint that terrain.
2. Create a Custom Underground Pockets layer (from the + button on the Layers panel). This will create random underground pockets of the material wherever you paint the layer. Good for things like underground ores or pockets of oil, etc.
3. Create a Custom Ground Cover layer. This will create a layer of the material on top of the surface. Make it one block thick and sprinkle the layer around for things like plants and flowers, or make it several blocks thick and paint it in solidly to create glaciers, etc.
4. Create a Custom Object Layer. This will load bo2 files and/or schematics and spawn them randomly on the map where you paint the layer. Schematics and bo2 files can contain custom blocks from mods if you export them from a map containing such blocks.

**Please note:** many mods have dynamic block ID's at runtime which are different than the block ID's stored on disk. The clue is often that these ID's are higher than 4095, which is not possible on disk. Make sure to find out from the mod's authors or documentation what the static, on-disk block ID's are and use those in WorldPainter.

### How do I control WorldPainter with a tablet?

WorldPainter support pressure sensitivity (to control the layer intensity or tool speed), eraser and pen buttons of tablets. Make sure the device driver for the tablet is installed and check the [Controls](https://www.worldpainter.net/trac/wiki/Controls) page for details.

### Why do I get chunk errors / missing chunks / weird square patches with water or different landscape after exporting the world?

Probably for one of two reasons:

* You Exported a world you previously Imported from an existing map, instead of Merging it with the map from which you imported it, which is what you should do with Imported worlds.
* You made changes to chunks that were marked read-only (with a black cross across them) and neglected to remove the read-only layer (by right-clicking with the Read-only button selected) from those chunks before Merging.

### How do I get it to create villages, ravines or strongholds?

WorldPainter can't generate any type of structure by itself. However it can direct Minecraft to generate structures in the generated map. You can do this by either selecting "allow Minecraft to populate the entire terrain" on the Export (or Dimension Properties) screen, to get them everywhere, or by painting in the Populate layer locally. Also make sure to leave the Structures option enabled on the Export screen.

**Please note** that WorldPainter has no control over _where_ these structures will be generated! Minecraft will place them randomly according to the seed and its own algorithms. Also, using Populate will also cause Minecraft to generate trees, tall grass and flowers, underground resources, small water and lava lakes everywhere. If you used WorldPainter's tree layers, or the Resource layer (which is on by default) you may get double the trees and/or resources.

If you don't want this, you do have one option: you can set the world type to Superflat, and then use the Superflat preset to configure exactly what you want Minecraft to do during the population step. For more details about this technique, see [​this YouTube video](https://www.youtube.com/watch?v=BMzq4fWEBrI) by Fornan II. For more details about the proper use of the Populate layer, see the [Populate](https://www.worldpainter.net/trac/wiki/Populate) page.

Note that you _could_ use custom object layers to add structures to the world. See the [CustomObjects](https://www.worldpainter.net/trac/wiki/CustomObjects) page for more details.

### How do I create arches, overhangs, floating islands or other types of overlapping land?

You can use [Custom Cave/Tunnel layers](https://www.worldpainter.net/trac/wiki/CavesAndTunnels) to achieve such effects. By setting the roof and ceiling heights and other settings judicously, you can configure a "cave" which is actually entirely above the ground of the valley, and will carve out overhangs, arches or other structures from the surrounding cliffs. For one example, see [​this YouTube video](https://www.youtube.com/watch?v=M-cPtwEwVY4) by Lord Dakr showing how to create arches.

### Why does my virus scanner say there is a virus, trojan or other malware in WorldPainter?

It is a false positive. There is no virus, trojan or other malware in WorldPainter. If your virus scanner says that there is, please report it to the makers as a false positive, and then use your virus scanner's "unquarantine" or equivalent functionality, or temporarily disable it, to be able to install and use WorldPainter. See the [FalsePositives](https://www.worldpainter.net/trac/wiki/FalsePositives) page for more information, including why you should upgrade to a better virus scanner.

### How do I add custom objects to my map?

For placing complete objects you can use a Custom Objects Layer. You need a copy of the object you want to place in bo2, bo3, schematic or nbt format. One way to do get these is to export the object from Minecraft using WorldEdit or MCEdit. You can also find collections of them online. Then create a Custom Objects Layer (from the + button on the Layers panel) and load the file (or multiple files).

See the [CustomObjects](https://www.worldpainter.net/trac/wiki/CustomObjects) page for more details (including links to online custom object collections). For an excellent tutorial by Lentebriesje, see [​here](http://www.planetminecraft.com/blog/how-to-use-custom-trees-and-objects-in-worldpainter/).

### How do I change what Minecraft does when I use Populate? How do I get rid of all the small water and lava lakes?

The small water and lava lakes aren't created by WorldPainter, they are created by Minecraft when you use the Populate layer, or enable the "allow Minecraft to populate the entire terrain" option. WorldPainter has no control over what Minecraft does when it populates a chunk, at least not for the Default and Large Biomes world types. All it can do is tell it to populate the chunk, or not, for each individual chunk. If Minecraft populates a chunk it will add underground resources, vegetation, trees, small water and lava lakes, snow and ice, villages, ravines, strongholds and abandoned mines. It will not generate caves. For more details about the proper use of the Populate layer, see the [Populate](https://www.worldpainter.net/trac/wiki/Populate) page.

If you don't want the small water and lava lakes, you do have one option: you can set the world type to Superflat, and then use the Superflat preset to configure exactly what you want Minecraft to do during the population step. For more details about this technique, see [​this YouTube video](https://www.youtube.com/watch?v=BMzq4fWEBrI) by Fornan II.

You should also consider whether you need Populate, as WorldPainter has its own layers for almost everything. The only thing that WorldPainter can't generate itself is structures (mines, villages, etc.). By default the Resources layer is "on everywhere", so WorldPainter already generates underground resources. You can use the other layers to add things like Deciduous or Pine forests, snow and ice, underground Caverns and Chasms, etc.

### How do I add custom brushes?

A custom brush is a grey scale bitmap image file. You can create it yourself using a paint program such as [​GIMP](https://www.gimp.org) or [​Paint.NET](https://www.getpaint.net) or download it off the Internet. Height maps of mountains, for instance, make good custom brush images. To install the custom brush, copy the image file to the custom brushes folder, which you can open from the Tools menu in WorldPainter. You have to restart WorldPainter for the custom brush to show up. For more details, see the [CustomBrushes](https://www.worldpainter.net/trac/wiki/CustomBrushes) page.

**Note**: you can organise the custom brushes into separate subdirectories inside the brushes folder, which will show up as separate palettes in WorldPainter. This is especially convenient if you have many custom brushes, to prevent the palette from becoming so large that it doesn't fit on the screen.

### How do I customise the biomes without creating any land, letting Minecraft generate the land according to the biomes?

Unfortunately due to the way Minecraft works this is not possible.

### How do I use the Populate layer?[ ¶](https://www.worldpainter.net/trac/wiki/FAQ#HowdoIusethePopulatelayer) <a href="#howdoiusethepopulatelayer" id="howdoiusethepopulatelayer"></a>

There is a lot of confusion about the correct usage of the Populate layer. [This](https://www.worldpainter.net/trac/wiki/Populate) page tries to explain exactly what it does and how to use it.

### How do I give WorldPainter more memory?

See the [Troubleshooting](https://www.worldpainter.net/trac/wiki/Troubleshooting) page, under "WorldPainter runs out of memory".
