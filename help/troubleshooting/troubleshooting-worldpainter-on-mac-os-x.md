# Troubleshooting WorldPainter  on Mac OS X

## Troubleshooting Mac OS X

For generic, non operating system specific troubleshooting information, check the [Troubleshooting](https://www.worldpainter.net/trac/wiki/Troubleshooting) page.

### I can't install WorldPainter/"worldpainter.dmg is damaged and can't be opened"

* If you have Mac OS X Mountain Lion or later it may refuse to install WorldPainter (while saying it is "damaged") because, while it is digitally signed, it is not signed by Apple (for which they charge $99 a year). Follow the instructions on [this](https://www.worldpainter.net/links/disable-gatekeeper) page to turn off the requirement for applications to be signed by Apple. Be sure to read the entire page; you may have to run a command to restore the ability to allow third party installs. You can turn it back on again after WorldPainter is installed.
* There are occasional download problems. Try downloading the installer again.

If you continue to have problems installing WorldPainter using one of the installers, you can try one of the installerless archives. You can find links to those on the same page where you downloaded the installer.

### WorldPainter just shows a light blue screen instead of the map

If you have a Mac with a Retina screen and Max OS X Mountain Lion, try following the instructions on [​this](http://support.apple.com/kb/HT5266) page to turn on the "Open in Low Resolution" setting for WorldPainter.

### WorldPainter won't start or is not usable any more[ ¶](https://www.worldpainter.net/trac/wiki/TroubleshootingMacOSX#WorldPainterwontstartorisnotusableanymore) <a href="#worldpainterwontstartorisnotusableanymore" id="worldpainterwontstartorisnotusableanymore"></a>

* If you made a change (such as installing custom brushes or a plugin, or changing a preference) and now WorldPainter won't start or is not usable any more, try using [WorldPainter Safe Mode](https://www.worldpainter.net/trac/wiki/SafeMode). It will allow WorldPainter to start and operate again, allowing you to undo the change you made, or confirm that the change was what caused the problem so you know to undo it.
* If that does not work, try resetting the preferences by deleting the WorldPainter configuration file (`~/Library/Application Support/WorldPainter/config`).
* You may have so many custom brushes installed that WorldPainter runs out of memory. The custom brushes are in `~/Library/Application Support/WorldPainter/brushes`, so if you have very many brushes in there, try culling them.
