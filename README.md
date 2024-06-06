# Welcome to the GeoLadder

This is a clone of the game Ladder originally written by Yahoo Software for various CP/M systems.

## Compile source

To compile it, you must choose the target language by setting only _one_ of the following defines in `ladder.goh`:

* `@define I8N_EN` for the Englsih language
* `@define I8N_DE` for the German language

Then do the usual compile:

```
mkmf
pmake depend
pmake
```

## Help files

The help files are provided in the source form as GeoWrite documents and as compiled GEOS help files. You'll find the files in the folder `Help`.

* `gladhsde.000` is the source help file in the German language
* `gladhsen.000` is the source help file in the English language

* `gladhcde.000` is the compiled help file in the German language
* `gladhcen.000` is the compiled help file in the English language

## Installation

Copy the compiled binary `geoladder.geo` to the `World` folder of your PC/GEOS installation. Shorten the filename to the 8.3 DOS convention if needed.

Depending on the compiled language, copy either the help file `gladhcde.000` or `gladhcen.000` to the `Userdata\Help` folder of your PC/GEOS installation.

## Known issues

There is a problem with the Watcom version of the SDK. The routine ChunkArrayGetElement() always returns the first element. Because to this, always the first level is loaded...

With this new Watcom based SDK, I have to use the routine ChunkOf() for references to other chunks. So, maybe there is another magic I miss.
