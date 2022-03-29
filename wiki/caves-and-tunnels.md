# Caves and Tunnels

## The Caves/Tunnels Layer

This page describes the various settings of the Caves/Tunnels custom layer type, and how to use them.

### Floor and Ceiling Heights

The heights of the floors and ceilings of the cave are configured separately. This way, you can mix and match them to create variously shaped caves or tunnels. The basic shape of both floor and ceiling are governed by two options; mode and level:

* **Fixed level** mode - the floor or ceiling is at a constant absolute height. The **level** parameter governs how many blocks above bedrock it will be. This setting makes flat floors or ceilings.
* **Fixed depth** mode - the floor or ceiling is at a constant depth beneath the surface. The **level** parameter governs how many blocks beneath the surface. This setting will make the floor or ceiling follow the contours of the land above it.
* **Opposite of terrain** mode - the floor or ceiling will have the _opposite_ shape of the terrain above; in other words where the terrain goes up the floor or ceiling will go down and where the terrain is higher the floor or ceiling will be deeper. The **level** parameter governs at what altitude the terrain will be 'reflected', or in other words, at what altitude the floor or ceiling will connect to the surface.
* For the _fixed depth_ and _opposite of terrain_ modes you can also set a **minimum** and **maximum** level. These set the absolute height which the floor or ceiling cannot drop below or rise above, and where it will therefore become flat.

A cave will only result in those locations where the ceiling level is higher than the floor level.

### Random Variation

The settings described above will result in completely flat floors and ceilings, and/or floors and ceilings that exactly follow or reflect the terrain. If you want more variation you can use the smoothness settings for both floor and ceiling to add some random noise:

* The **range** setting determines the height of the random variations. 0 means no variation at all (in which case the other settings aren't applicable and therefore disabled). If you set this higher than 0 the floor or ceiling will have random "hills" with the configured number of blocks difference between the lowest troughs and highest peaks. Note that the displacement is both up _and_ down, centred around the original floor or ceiling height.
* The **scale** setting determines the horizontal size of the "hills". If you set this lower the peaks will be narrower, sharper and closer together, if you set it higher they will be wider and further apart.
* The **roughness** setting determines how chaotic or rough the "hills" are. At 0 they are smooth and very similar to WorldPainter's default terrain. At higher levels more and more smaller detail is introduced to make the terrain more rough or chaotic.

### Walls

The settings described so far will result in perfectly flat walls that meet the floors and ceilings at 90 degree angles (or whatever angle the floor or ceiling is at). If you want smoother transitions of floors to walls and walls to ceilings you can do so with the **bottom width** and **top width** settings. These determine how far, in blocks, the wall will come 'into' the cave at the bottom and top of the wall, respectively. From there, the wall will make a quarter circular turn upwards or downwards, so the height of the section that comes into the cave will be the same as the width (unless the cave is not high enough for that of course).

If you want a **square** cave or tunnel, set these to 0. If you want a perfectly **circular** cave or tunnel, set them to half the cave height (the difference between the floor and ceiling levels), and make sure to paint the layer at the correct width by setting the brush radius to the same value.

### Water and Lava

There are two water and lava related options you can set:

* The **remove water or lava** option controls whether existing water (or lava) will be removed and floors, walls and ceilings rendered underwater (when on), or whether existing water (or lava) will be left in place and floor, wall and ceiling blocks _not_ placed underwater (when off - the default). Note that this only applies to water or lava from WorldPainter terrain generation or the Flood or Lava tools, _not_ to water from the Resources layer or custom layers.
* The **flood the caves/tunnels** option controls whether the generated caves/tunnels will be flooded. You control the **level** to which they will be flooded, as well as whether they are flooded with water or **lava**

### The Preview

The Caves/Tunnels custom layer settings screen includes a preview which shows the effect of the settings discussed above, making it easier to configure the layer to your liking. Note that the landscape shown is _not_ the actual landscape from your map! It's a fixed landscape intended to include a range of terrain heights in order to be able to judge the effects of any height settings.

The preview cave/tunnel ends a short distance from the right edge, so you can see the effects of the _bottom extent_ and _top extent_ wall depth settings.

### Layer Colouring

Depending on the settings you chose, the layer may not actually produce caves everywhere you paint it. If the floor height is higher than the terrain height where you paint the layer, for instance, a cave will obviously not be produced. Also, the combination of floor and ceiling modes and levels might result in there not being any cave at all where the terrain is too low (for instance when the ceiling is set to _fixed depth_ and the floor to _fixed level_ or _opposite of terrain_).

Similarly, a cave might not be entirely underground. If the floor is below ground level, but the ceiling is above it, the cave will break the surface and be open to the outside air.

To be able to better judge this, the cave layer will be painted in different intensities:

* **Lighter shade** - if there is no cave at all as a result of the combination of floor and ceiling modes and levels and terrain height, or if the cave is entirely above the surface, and the layer will therefore not have any effect at all.
* **Darker shade** - if there will be a cave, and it is entirely underground - i.e. both floor and ceiling are below surface level.
* **Solid** - if there will be a cave, and it breaks the surface - i.e. the floor is below surface level but the ceiling is above it. This allows you to quickly see where tunnel entrances and exits will be, and to adjust the terrain after painting a cave to fix "holes" where the cave breaks through to the surface unintentionally. **Note** that this is only approximate though! It does not take the wall depth settings or random variation into account.

### Materials

By default, the cave or tunnel will just be excavated out of the blocks that are already there, so the floors, walls and ceilings will be made of whatever the underground material happens to be in that location.

If you want the floors, walls and ceilings to be made of a particular kind of material you can do so by setting the **material** option in the corresponding section(s). You have the same mixed material options as when configuring a custom terrain type. You can leave it at just one block type, or you can configure a mix of different block types.

The floor and ceiling materials are only used for the "actual" floors and ceilings, in other words only those parts which aren't the wall extending into the cave, or have random variation applies to them. The walls material setting includes the parts of the wall that extend into the cave, as well as any random variation of cloors and ceilings, so in rougher, more natural looking caves the walls material will actually probably be by far the most prevalent.

You don't have to set a material for every section. You can have a floor made of Bricks or Stone Bricks or something like that, for instance, while leaving the walls and ceilings natural.

### Tips and Tricks

* Use a **solid brush and 100% intensity** for painting the layer! (Although having some noisy edges _can_ give interesting effects, so experiment with it.)
* **Keep the caves small**. What seems small in the editor quickly becomes huge in Minecraft. Also, if the cave is too large Minecraft's distance fog will light it up weirdly and unnaturally. Keep your tunnels and caves smaller than your initial instinct tells you to.
* **Make your tunnels winding**. Again, this helps prevent the Minecraft fog from lighting up your tunnels.
* If there are no other caves around for mobs to spawn in your caves and tunnels will be crawling with them. **Consider adding some generic caves** in the neighbourhood using the Caverns layer, which you don't necessarily intend players to find but which will absorb mobs.
* Instead of trying to adjust the layer parameters to stop it breaking the surface unintentionally, it may be easier to just **adjust the terrain after painting the caves**. The fact that the layer turns solid where it breaks the surface makes it very easy to adjust the terrain until all solid patches are gone.

### Example

Here is an example world with a few samples of Caves/Tunnel layer usage. Everything you see in the map, including the halls and hallways, is created with the Caves/Tunnels layer:

[​Minecraft map](http://www.worldpainter.net/files/maps/CavesAndTunnelsExample.zip)\
[​WorldPainter file](http://www.worldpainter.net/files/worlds/CavesAndTunnelsExample.world)
