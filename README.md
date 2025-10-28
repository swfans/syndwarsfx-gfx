# syndwarsfx-gfx

Source graphics files for Syndicate Wars Fan Expansion.

## About

**Syndicate Wars Fan Expansion**, alternative binary for the classic Bullfrog game.

Alongside fixes to the game executable code, an updated set of assets is
required to use the full potential of the code fixes.

This repository contains the original sprites and animations developed by
Bullfrog, with additional fixes applied to the files by fan community.

## Installation from a release

Download the release `syndwarsfx-gfx-*.zip` file. Copy the extracted
`DATA` folder to a previous SyndWarsFX installation,
replacing the existing files.

### General building instructions

To build **SyndWarsFX GFX**, use the following steps:

1. download [pngpal2raw](https://github.com/swfans/pngpal2raw/releases/),
   place the binary in `syndwarsfx-gfx/bin` or any folder included in `PATH` env var.
2. go into the directory with `syndwarsfx-gfx` source release
3. do `autoreconf -if` to create build scripts from templates
4. do `./configure` to make the build scripts find required dependencies
5. do `make` to build release versions of data files
6. do `make install` to copy the files into `syndwarsfx` installation folder

You should now have the latest DAT/TAB/ANI files in your installation folder.

#### Build example - Ubuntu 20.04 64-bit

Here are specific commands required to build the gfx on Ubuntu linux.

Download the `syndwarsfx-gfx` source release, and extract it somewhere.

Also download latest release of the [pngpal2raw](https://github.com/swfans/pngpal2raw/releases/),
and extract the binary into `bin` sub-folder of the place with `syndwarsfx-gfx`.
If you've downloaded the `.zip` to `syndwarsfx-sfx` folder, you can just go there and run:

```
unzip -j -d ./bin/ pngpal2raw-*-ubuntu.zip
```

Being still in the `syndwarsfx-gfx` folder, generate build scripts from templates using
autotools:

```
autoreconf -ivf
```

Next, proceed with the build steps; we will do that in a separate folder.

```
mkdir -p release; cd release
../configure
make V=1
```

The `V=1` variable makes `make` print each command it executes, which makes
diagnosing issues easier.

You can use `make install` to add the files to your installation, or copy
them to a new folder from which you may copy them manually.

To copy output files to a `pkg` folder, creating  proper sub-folders for
release, use:


```
make V=1 DESTDIR=$PWD/pkg install
```

That's it, now you have the DAT/TAB/ANI files ready.

## Done

That's all. See more documentation in [SyndWarsFX repo](https://github.com/swfans/syndwarsfx).
