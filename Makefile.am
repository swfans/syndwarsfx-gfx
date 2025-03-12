ACLOCAL_AMFLAGS = --install -I m4

gfxani_DATA = $(wildcard $(top_srcdir)/data/*.ani)
gfxanidir = $(prefix)/$(PARENT_PACKAGE)/data

mouse0_DATA = data/mouse0-1.dat data/mouse0-1.tab
mouse0dir = $(prefix)/$(PARENT_PACKAGE)/data

data/mouse0-1.tab: data/mouse0-1.dat

data/mouse0-1.dat: $(top_srcdir)/femouse-64/filelist-mouse0-1.txt $(top_srcdir)/data/feproj-std.pal

pointr0_DATA = data/pointr0-3.dat data/pointr0-3.tab data/pointr0-1.dat data/pointr0-1.tab data/pointr0-0.dat data/pointr0-0.tab
pointr0dir = $(prefix)/$(PARENT_PACKAGE)/data

data/pointr0-3.tab: data/pointr0-3.dat

data/pointr0-3.dat: $(top_srcdir)/pointers-128/filelist-pointr0-3.txt $(top_srcdir)/data/engine-std.pal

data/pointr0-1.tab: data/pointr0-1.dat

data/pointr0-1.dat: $(top_srcdir)/pointers-64/filelist-pointr0-1.txt $(top_srcdir)/data/engine-std.pal

data/pointr0-0.tab: data/pointr0-0.dat

data/pointr0-0.dat: $(top_srcdir)/pointers-32/filelist-pointr0-0.txt $(top_srcdir)/data/engine-std.pal

include $(srcdir)/sprites-fontc0-0.am
include $(srcdir)/sprites-fontc0-1.am
include $(srcdir)/sprites-fontc0-3.am
include $(srcdir)/sprites-fontc0-7.am
include $(srcdir)/sprites-fontc1-0.am
include $(srcdir)/sprites-fontc1-2.am
include $(srcdir)/sprites-fontc2-0.am
include $(srcdir)/sprites-fontc2-1.am
include $(srcdir)/sprites-fontc2-3.am
include $(srcdir)/sprites-fontc2-7.am

font0_DATA = $(fontc0_0_files) $(fontc0_1_files) $(fontc0_3_files) $(fontc0_7_files) \
  $(fontc1_0_files) $(fontc1_2_files) \
  $(fontc2_0_files) $(fontc2_1_files) $(fontc2_3_files) $(fontc2_7_files)
font0dir = $(prefix)/$(PARENT_PACKAGE)/data

include $(srcdir)/sprites-pop0-0.am
include $(srcdir)/sprites-pop0-1.am
include $(srcdir)/sprites-pop0-3.am
include $(srcdir)/sprites-pop1-0.am
include $(srcdir)/sprites-pop1-1.am
include $(srcdir)/sprites-pop1-3.am
include $(srcdir)/sprites-pop2-0.am
include $(srcdir)/sprites-pop2-1.am
include $(srcdir)/sprites-pop2-3.am

include $(srcdir)/sprites-panel0-0.am
include $(srcdir)/sprites-panel0-1.am
include $(srcdir)/sprites-panel0-3.am
include $(srcdir)/sprites-panel1-0.am
include $(srcdir)/sprites-panel1-1.am
include $(srcdir)/sprites-panel1-3.am
include $(srcdir)/sprites-panel2-0.am
include $(srcdir)/sprites-panel2-1.am
include $(srcdir)/sprites-panel2-3.am

pop0_DATA = $(pop0_0_files) $(pop0_1_files) $(pop0_3_files) $(pop1_0_files) \
  $(pop1_1_files) $(pop1_3_files) $(pop2_0_files) $(pop2_1_files) $(pop2_3_files) \
  $(panel0_0_files) $(panel0_1_files) $(panel0_3_files) $(panel1_0_files) \
  $(panel1_1_files) $(panel1_3_files) $(panel2_0_files) $(panel2_1_files) $(panel2_3_files)
pop0dir = $(prefix)/$(PARENT_PACKAGE)/data

data/%.dat:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f sspr -l 0 "$<"

include $(srcdir)/sprites-eng-icons0-1.am

eng_icons0_DATA = $(eng_icons0_1_files)
eng_icons0dir = $(prefix)/$(PARENT_PACKAGE)/language/eng

language/eng/%.dat:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f sspr -l 0 "$<"

include $(srcdir)/sprites-fre-icons0-1.am

fre_icons0_DATA = $(fre_icons0_1_files)
fre_icons0dir = $(prefix)/$(PARENT_PACKAGE)/language/fre

language/fre/%.dat:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f sspr -l 0 "$<"

include $(srcdir)/sprites-ger-icons0-1.am

ger_icons0_DATA = $(ger_icons0_1_files)
ger_icons0dir = $(prefix)/$(PARENT_PACKAGE)/language/ger

language/ger/%.dat:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f sspr -l 0 "$<"

include $(srcdir)/sprites-ita-icons0-1.am

ita_icons0_DATA = $(ita_icons0_1_files)
ita_icons0dir = $(prefix)/$(PARENT_PACKAGE)/language/ita

language/ita/%.dat:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f sspr -l 0 "$<"

include $(srcdir)/sprites-spa-icons0-1.am

spa_icons0_DATA = $(spa_icons0_1_files)
spa_icons0dir = $(prefix)/$(PARENT_PACKAGE)/language/spa

language/spa/%.dat:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f sspr -l 0 "$<"

include $(srcdir)/sprites-swe-icons0-1.am

swe_icons0_DATA = $(swe_icons0_1_files)
swe_icons0dir = $(prefix)/$(PARENT_PACKAGE)/language/swe

language/swe/%.dat:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f sspr -l 0 "$<"

include $(srcdir)/anims-wep-mod.am

eqwepmod0_DATA = $(equip_wep_files) $(equip_mod_files)
eqwepmod0dir = $(prefix)/$(PARENT_PACKAGE)/data/equip

data/equip/%.fli:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f flic -l 0 "$<"

include $(srcdir)/anims-cyborg.am

cybermod0_DATA = $(cyborg_nomotion_i_files) $(cyborg_nomotion_o_files) $(cyborg_inmotion_files) $(cyborg_static_files)
cybermod0dir = $(prefix)/$(PARENT_PACKAGE)/qdata/equip

include $(srcdir)/campaign.am

campaign0_DATA = $(campaign_raw_files)
campaign0dir = $(prefix)/$(PARENT_PACKAGE)/qdata

qdata/equip/%.fli:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f flic -l 0 "$<"

qdata/equip/%.raw:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -o "$@" -p "$(word 2,$^)" -f raw -l 0 "$<"

docs_DATA = README.md gfx_config.h
docsdir = $(prefix)/$(PARENT_PACKAGE)

EXTRA_DIST = gfxani docs mouse0 pointr0 font0 pop0 eng_icons0 fre_icons0 ger_icons0 ita_icons0 spa_icons0 swe_icons0 eqwepmod0 cybermod0 campaign0

install-data-hook:
	cd "$(DESTDIR)${prefix}/$(PARENT_PACKAGE)"; \
	mv README.md gfx_readme.md
