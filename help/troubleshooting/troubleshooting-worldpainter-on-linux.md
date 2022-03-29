# Troubleshooting WorldPainter  on Linux

## Troubleshooting Linux

For generic, non operating system specific troubleshooting information, check the [Troubleshooting](https://www.worldpainter.net/trac/wiki/Troubleshooting) page.

### I can't find WorldPainter after installation? How do I start WorldPainter?

If you installed the .deb or .rpm package, WorldPainter is installed in `/opt/worldpainter`. Try starting it from a terminal window with the command:

```
/opt/worldpainter/worldpainter
```

If you used the installer (the .sh package), or an installerless archive, then you specified the installation directory when you installed the program. Try executing the worldpainter command from the installation directory using something like this from a terminal window:

```
/path/to/worldpainter/worldpainter
```

### WorldPainter won't start or is not usable any more

* If you made a change (such as installing custom brushes or a plugin, or changing a preference) and now WorldPainter won't start or is not usable any more, try using [WorldPainter Safe Mode](https://www.worldpainter.net/trac/wiki/SafeMode). It will allow WorldPainter to start and operate again, allowing you to undo the change you made, or confirm that the change was what caused the problem so you know to undo it.
* If that does not work, try resetting the preferences by deleting the WorldPainter configuration file (`~/.worldpainter/config`).
* You may have so many custom brushes installed that WorldPainter runs out of memory. The custom brushes are in `~/.worldpainter/brushes`, so if you have very many brushes in there, try culling them.
