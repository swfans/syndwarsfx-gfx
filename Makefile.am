ACLOCAL_AMFLAGS = --install -I m4

gfxani_DATA = $(wildcard $(top_srcdir)/data/*.ani)
gfxanidir = $(prefix)/$(PARENT_PACKAGE)/data

mouse0_DATA = data/mouse0-1.dat data/mouse0-1.tab
mouse0dir = $(prefix)/$(PARENT_PACKAGE)/data

data/mouse0-1.tab: data/mouse0-1.dat

data/mouse0-1.dat: $(top_srcdir)/femouse-64/filelist-mouse0-1.txt $(top_srcdir)/data/feproj-std.pal

pointr0_DATA = data/pointr0-2.dat data/pointr0-2.tab data/pointr0-1.dat data/pointr0-1.tab data/pointr0-0.dat data/pointr0-0.tab
pointr0dir = $(prefix)/$(PARENT_PACKAGE)/data

data/pointr0-2.tab: data/pointr0-2.dat

data/pointr0-2.dat: $(top_srcdir)/pointers-128/filelist-pointr0-2.txt $(top_srcdir)/data/engine-std.pal

data/pointr0-1.tab: data/pointr0-1.dat

data/pointr0-1.dat: $(top_srcdir)/pointers-64/filelist-pointr0-1.txt $(top_srcdir)/data/engine-std.pal

data/pointr0-0.tab: data/pointr0-0.dat

data/pointr0-0.dat: $(top_srcdir)/pointers-32/filelist-pointr0-0.txt $(top_srcdir)/data/engine-std.pal

font0_DATA = data/font0-2.dat data/font0-2.tab
font0dir = $(prefix)/$(PARENT_PACKAGE)/data

# List of font letters which can be colorized
font0_chars = \
  0021 0022 0023 0024 0025 0026 0027 0028 0029 002a 002b 002c 002d 002e 002f \
  0030 0031 0032 0033 0034 0035 0036 0037 0038 0039 003a 003b 003c 003d 003e 003f \
  0040 0041 0042 0043 0044 0045 0046 0047 0048 0049 004a 004b 004c 004d 004e 004f \
  0050 0051 0052 0053 0054 0055 0056 0057 0058 0059 005a 005b 005c 005d 005e 005f \
  00a1 00aa 00b0 00bf 00c0 00c1 00c4 00c5 00c7 00c8 00c9 00cc 00cd \
  00d1 00d2 00d3 00d6 00d9 00da 00dc 00df
# List of non-letters or other sprites to pass without colorization
font0_charnames_nomod = \
  empty char_u0020
font0_sprites_gen = \
  $(foreach num,$(font0_chars),font0_sharp_cult-23-ltblue/char_u$(num).png)
font0_sprites_cp = \
  $(foreach name,$(font0_charnames_nomod),$(top_srcdir)/font0_sharp_cult-23-white/$(name).png)

data/font0-2.tab: data/font0-2.dat

data/font0-2.dat: font0_sharp_cult-23-ltblue/filelist-font0-2.txt $(top_srcdir)/data/feproj-std.pal $(font0_sprites_gen)

font0_sharp_cult-23-ltblue/filelist-font0-2.txt: $(top_srcdir)/font0_sharp_cult-23-white/filelist-font0-2.txt
	$(MKDIR_P) "$(@D)"
	cp -p -t "$(@D)" $(font0_sprites_cp)
	cp -p "$<" "$@"

docs_DATA = README.md gfx_config.h
docsdir = $(prefix)/$(PARENT_PACKAGE)

EXTRA_DIST = gfxani docs mouse0 pointr0 font0

# Use ImageMagick to generate light blue sprites from the white ones
font0_sharp_cult-23-ltblue/%.png: $(top_srcdir)/font0_sharp_cult-23-white/%.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK) "$<" -colorspace RGB \
        -channel R -evaluate multiply 0.66 \
        -channel G -evaluate multiply 0.53 \
        -channel B -evaluate multiply 0.99 \
        +channel -colorspace RGB "$@"

data/%.dat:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f sspr -l 0 "$<"

install-data-hook:
	cd "$(DESTDIR)${prefix}/$(PARENT_PACKAGE)"; \
	mv README.md gfx_readme.md
