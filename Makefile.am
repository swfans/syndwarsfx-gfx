ACLOCAL_AMFLAGS = --install -I m4

gfxani_DATA = $(wildcard $(top_srcdir)/data/*.ani)
gfxanidir = $(prefix)/$(PARENT_PACKAGE)/data

mouse0_DATA = data/mouse0-1.dat
mouse0dir = $(prefix)/$(PARENT_PACKAGE)/data

data/mouse0-1.dat: $(top_srcdir)/femouse-64/filelist-mouse0-1.txt $(top_srcdir)/data/feproj-std.pal

pointr0_DATA = data/pointr0-1.dat data/pointr0-1.tab data/pointr0-0.dat data/pointr0-0.tab
pointr0dir = $(prefix)/$(PARENT_PACKAGE)/data

data/pointr0-1.tab: data/pointr0-1.dat

data/pointr0-0.tab: data/pointr0-0.dat

data/pointr0-1.dat: $(top_srcdir)/pointers-64/filelist-pointr0-1.txt $(top_srcdir)/data/engine-std.pal

data/pointr0-0.dat: $(top_srcdir)/pointers-32/filelist-pointr0-0.txt $(top_srcdir)/data/engine-std.pal

docs_DATA = gfx_config.h
docsdir = $(prefix)/$(PARENT_PACKAGE)

EXTRA_DIST = gfxani docs mouse0 pointr0

data/%.dat:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f sspr -l 0 "$<"
