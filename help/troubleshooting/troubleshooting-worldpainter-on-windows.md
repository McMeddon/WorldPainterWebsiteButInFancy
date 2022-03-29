# Troubleshooting WorldPainter on Windows

## Troubleshooting Windows

For generic, non operating system specific troubleshooting information, check the [Troubleshooting](https://www.worldpainter.net/trac/wiki/Troubleshooting) page.

### "Could not find Java on your computer"/"The JVM (...) is damaged"

Assuming you have actually got Java installed, the problem is probably that it is the wrong word size (number of bits).

On 32-bit Windows you should be using the 32-bit version of WorldPainter (it should have `_32` in the file name of the installer), and the 32-bit version of Java. You can download 32-bit Java [here](https://www.worldpainter.net/links/jre-win-32) (pick the file ending in `-i586.exe`).

On 64-bit Windows, you should be using the 64-bit version of WorldPainter (it should _not_ have `_32` in the file name of the installer), and the 64-bit version of Java. You can download 64-bit Java [here](https://www.worldpainter.net/links/jre-win-64) (pick the file ending in `.exe`).

You should always be using the version of Java installed in `Program Files` (not `Program Files (x86)`). On 64-bit Windows, 32-bit Java is installed in `Program Files (x86)`, and is the wrong version.

#### How do I know if I have 32 or 64-bit Windows?

Check if you have a `Program Files (x86)` directory (so _with_ the `(x86)`). If you do, it is 64-bit Windows, if not, it is 32-bit Windows.

### I can't install WorldPainter

There are occasional download problems. Try downloading the installer again. If that doesn't fix the problem, check below:

* Make sure you're using the installer for the right word size (32 or 64 bit). If you're not sure, try the 64-bit installer first, if that doesn't work, try the 32-bit installer.
* It is possible that a custom Windows theme is triggering a bug in Java and preventing the installer from starting. Try checking "Disable visual themes" on the Compatibility tab of the installer file's properties, or if that does not work either, resetting the Windows theme to the default altogether. If checking the "disable visual themes" option worked you will probably have to do it for the shortcut for WorldPainter proper after the installation as well.
* Make sure you are using a complete and legal copy of Windows, not a "light" or "modded" version which may lack components that the installer, or WorldPainter itself, needs.
* Try temporarily disabling any firewalls or virus/malware scanners you may have installed, or other software which might be interfering with the download or installation process.

If you continue to have problems installing WorldPainter using one of the installers, you can try one of the installerless archives. You can find links to those on the same page where you downloaded the installer. Note that that won't work if the problem is using a custom theme on Windows though!

### WorldPainter won't start or is not usable any more

* If you made a change (such as installing custom brushes or a plugin, or changing a preference) and now WorldPainter won't start or is not usable any more, try using [WorldPainter Safe Mode](https://www.worldpainter.net/trac/wiki/SafeMode). It will allow WorldPainter to start and operate again, allowing you to undo the change you made, or confirm that the change was what caused the problem so you know to undo it.
* It is possible you made some kind of modification to the preferences that cause it to no longer start, for instance setting the default size larger than you have memory for. Try resetting the preferences by deleting the WorldPainter configuration file (`%APPDATA%\WorldPainter\config`).
* You may have so many custom brushes installed that WorldPainter runs out of memory. The custom brushes are in `%APPDATA%\WorldPainter\brushes`, so if you have very many brushes in there, try culling them.
* It is possible that a custom Windows theme is triggering a bug in Java and preventing WorldPainter from starting. Try checking "Disable visual themes" on the Compatibility tab of the WorldPainter shortcut properties, or if that does not work, resetting the Windows theme to the default altogether.

### WorldPainter looks bad on high resolution displays

WorldPainter tries to detect high resolution displays and adjust the size of its user interface, but on newer Java versions this does not work correctly and looks bad. Until this can be fixed in WorldPainter you can let Windows do the scaling, which looks less bad:

* Find the WorldPainter start menu entry by opening the start menu and typing WorldPainter (but don't press Enter or click on it)
* Right-click on the WorldPainter start menu entry and select "Open file location". This will open an Explorer window with the WorldPainter start menu entries in it
* In that window, right-click on WorldPainter and select Properties
* Go to the Compatibility tab
* Click on "Change high DPI settings"
* Select "Override high DPI scaling behavior."
* Under "Scaling performed by:", select "System"
* Click OK and OK

When you next start WorldPainter Windows should do the scaling, which looks a little out of focus, but better than WorldPainter's own algorithm.
