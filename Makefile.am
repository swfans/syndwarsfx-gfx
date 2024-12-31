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

# Use ImageMagick to generate light blue sprites from the white ones
font0_sharp_cult-23-ltblue/%.png: $(top_srcdir)/font0_sharp_cult-23-white/%.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) "$<" -colorspace RGB \
        -channel R -evaluate multiply 0.66 \
        -channel G -evaluate multiply 0.53 \
        -channel B -evaluate multiply 0.99 \
        +channel -colorspace RGB "$@"

# Use ImageMagick to generate light teal sprites from the white ones
font0_sharp_cult-20-ltteal/%.png: $(top_srcdir)/font0_sharp_cult-20-white/%.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) "$<" -colorspace RGB \
        -channel R -evaluate multiply 0.00 \
        -channel G -evaluate multiply 0.99 \
        -channel B -evaluate multiply 0.99 \
        +channel -colorspace RGB "$@"

pop0_DATA = data/pop0-1.dat data/pop0-1.tab
pop0dir = $(prefix)/$(PARENT_PACKAGE)/data

pop0_chars_text_detail = \
  0044 0045 0054 0041 0049 004c

pop0_chars_text_uplink = \
  0055 0050 004c 0049 004e 004b 0020

pop0_chars_text_paused = \
  0050 0041 0055 0053 0045 0044

weapons_singl_outline = \
  uzi minigun laser ellaser rap persuader flamer h2htaser longrange airstrike beam razorwire \
  qdevastator persuader2 stasisfld soulgun time cerberusiff medi1 medi2 explwire cloneshld item_cybmod item_suitcase
weapons_fourp_outline = \
  nuclgren crazygas kogas elemine explmine

pop0_sprites_text_detail = \
  $(foreach num,$(pop0_chars_text_detail),font0_sharp_cult-20-ltteal/char_u$(num).png)

pop0_sprites_text_uplink = \
  $(foreach num,$(pop0_chars_text_uplink),font0_sharp_cult-20-ltteal/char_u$(num).png)

pop0_sprites_text_paused = \
  $(foreach num,$(pop0_chars_text_paused),font0_sharp_cult-20-ltteal/char_u$(num).png)

pop0_sprites_text = \
  panel_lblue_plain-64-baked/text_detail.png \
  panel_lblue_plain-64-baked/text_uplink.png \
  panel_lblue_plain-64-baked/text_paused.png

pop0_sprites_wep_oln = \
  $(foreach name,$(weapons_singl_outline),panel_lblue_plain-64-baked/weapon_outline_$(name).sngl.lgt.png) \
  $(foreach name,$(weapons_fourp_outline),panel_lblue_plain-64-baked/weapon_outline_$(name).foup.lgt.png)
pop0_sprites_wep_pnl = \
  $(foreach name,$(weapons_singl_outline),panel_lblue_plain-64-baked/weapon_outline_$(name).sngl.nrm.png) \
  $(foreach name,$(weapons_fourp_outline),panel_lblue_plain-64-baked/weapon_outline_$(name).foup.nrm.png)

pop0_sprites_agents_panel = \
  $(foreach num,1 2 3 4,panel_lblue_plain-64-baked/panel_peragent_main_number_$(num).png) \
  $(foreach name,nrm lgt,panel_lblue_plain-64-baked/panel_peragent_supl_medi.$(name).png) \
  panel_lblue_plain-64-baked/panel_peragent_supl_hlight.png \
  panel_lblue_plain-64-baked/panel_weapon_frame_hlight.png \
  panel_lblue_plain-64-baked/panel_weapon_list_frst_hlight.png \
  panel_lblue_plain-64-baked/panel_weapon_list_next_hlight.png

# List of sprites to pass without alterations
pop0_sprnames_nomod = \
  frame1_med_lgt_bl frame1_med_lgt_br frame1_med_lgt_tl frame1_med_lgt_tr frame1_med_nrm_bl frame1_med_nrm_br frame1_med_nrm_tl frame1_med_nrm_tr \
  empty kicked_arrow_left kicked_arrow_right \
  ingame_agent_number_1 ingame_agent_number_2 ingame_agent_number_3 ingame_agent_number_4 \
  panel_agent_number_1 panel_agent_number_2 panel_agent_number_3 panel_agent_number_4 \
  panel_grouping panel_grouping_bar_grp panel_grouping_bar_th \
  panel_peragent_supl_empty panel_peragent_supl_symbol_medi \
  panel_sshield_ena_btm panel_sshield_ena_top panel_sshield_nrm_btm panel_sshield_nrm_top panel_weapon_frame \
  panel_weapon_list_frst_frame panel_weapon_list_next_frame weapon_bk_empty
pop0_sprites_cp = \
  $(foreach name,$(pop0_sprnames_nomod),panel_lblue_plain-64-baked/$(name).png)

data/pop0-1.tab: data/pop0-1.dat

data/pop0-1.dat: panel_lblue_plain-64-baked/filelist-pop0-1.txt $(top_srcdir)/data/engine-std.pal ${pop0_sprites_cp} $(pop0_sprites_text) $(pop0_sprites_agents_panel) $(pop0_sprites_wep_oln) $(pop0_sprites_wep_pnl)

panel_lblue_plain-64-baked/%.txt: $(top_srcdir)/panel_lblue_plain-64/%.txt
	$(MKDIR_P) "$(@D)"
	cp -p "$<" "$@"

panel_lblue_plain-64-baked/%.png: $(top_srcdir)/panel_lblue_plain-64/%.png
	$(MKDIR_P) "$(@D)"
	cp -p "$<" "$@"

panel_lblue_plain-64-baked/text_detail.png: $(pop0_sprites_text_detail)
	$(MKDIR_P) "$(@D)"
	$(MAGICK_MONTAGE) $+ -background none -tile 9x1 -geometry +0+0 miff:- | $(MAGICK_CONVERT) - -crop 106x20+0+3 +repage "$@"

panel_lblue_plain-64-baked/text_uplink.png: $(pop0_sprites_text_uplink)
	$(MKDIR_P) "$(@D)"
	$(MAGICK_MONTAGE) $+ -background none -tile 9x1 -geometry +0+0 miff:- | $(MAGICK_CONVERT) - -crop 142x20+0+3 +repage "$@"

panel_lblue_plain-64-baked/text_paused.png: $(pop0_sprites_text_paused)
	$(MKDIR_P) "$(@D)"
	$(MAGICK_MONTAGE) $+ -background none -tile 9x1 -geometry +0+0 miff:- | $(MAGICK_CONVERT) - -crop 128x20+0+3 +repage "$@"

# Use ImageMagick to generate light teal sprites from the white ones
# rule with multiple targets is automatically divided into multiple rules with single target
panel_lblue_plain-64-baked/%.sngl.lgt.png panel_lblue_plain-64-baked/%.foup.lgt.png: $(top_srcdir)/weapons-outline-18/%.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) "$<" -colorspace RGB \
        -channel R -evaluate multiply 0.00 \
        -channel G -evaluate multiply 0.99 \
        -channel B -evaluate multiply 0.99 \
        +channel -colorspace RGB "$@"

panel_lblue_plain-64-baked/panel_peragent_main_number_1.png: $(top_srcdir)/panel_lblue_plain-64/panel_peragent_frst_empty.png panel_lblue_plain-64-baked/panel_agent_number_1.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) $< \( "$(word 2,$+)" -normalize +level 0,79% \) -gravity Center -geometry -60-6 -composite "$@"

panel_lblue_plain-64-baked/panel_peragent_main_number_2.png: $(top_srcdir)/panel_lblue_plain-64/panel_peragent_next_empty.png panel_lblue_plain-64-baked/panel_agent_number_2.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) $< \( "$(word 2,$+)" -normalize +level 0,79% \) -gravity Center -geometry -55-2 -composite "$@"

panel_lblue_plain-64-baked/panel_peragent_main_number_3.png: $(top_srcdir)/panel_lblue_plain-64/panel_peragent_next_empty.png panel_lblue_plain-64-baked/panel_agent_number_3.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) $< \( "$(word 2,$+)" -normalize +level 0,79% \) -gravity Center -geometry -55-2 -composite "$@"

panel_lblue_plain-64-baked/panel_peragent_main_number_4.png: $(top_srcdir)/panel_lblue_plain-64/panel_peragent_next_empty.png panel_lblue_plain-64-baked/panel_agent_number_4.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) $< \( "$(word 2,$+)" -normalize +level 0,79% \) -gravity Center -geometry -57-2 -composite "$@"

panel_lblue_plain-64-baked/panel_peragent_supl_medi.nrm.png: $(top_srcdir)/panel_lblue_plain-64/panel_peragent_supl_empty.png panel_lblue_plain-64/panel_peragent_supl_symbol_medi.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) $< \( "$(word 2,$+)" -normalize +level 0,79% \) -gravity Center -geometry +0+0 -composite "$@"

panel_lblue_plain-64-baked/panel_peragent_supl_medi.lgt.png: $(top_srcdir)/panel_lblue_plain-64/panel_peragent_supl_empty.png panel_lblue_plain-64/panel_peragent_supl_symbol_medi.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) $+ -gravity Center -geometry +0+0 -composite "$@"

panel_lblue_plain-64-baked/%.sngl.nrm.png: panel_lblue_plain-64-baked/weapon_bk_empty.png panel_lblue_plain-64-baked/%.sngl.lgt.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) $< \( "$(word 2,$+)" -normalize +level 0,79% \) -gravity Center -geometry +0+0 -composite "$@"

panel_lblue_plain-64-baked/%.foup.nrm.png: panel_lblue_plain-64-baked/weapon_bk_empty.png panel_lblue_plain-64-baked/%.foup.lgt.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) $< \( "$(word 2,$+)" -normalize +level 0,79% \) -gravity Center -geometry +0+0 -composite \
        -channel A -region 4x4-26+7 -negate -region 4x4-26-7 -negate -region 4x4+26+7 -negate -region 4x4+26-7 -negate +channel "$@"

# Use ImageMagick to generate light teal highlight border sprites around medikit box
# 1. convert non-transparent areas to white, transparent to black
# 2. remove the transparency; add extra 4px black border (to make border detection work at edges)
# 3. detect borders using Laplacian filter convolution
# 4. remove the border again, make all non-black pixels white, and black pixels transparent
# 5. multiply the pixels to achieve expected border color
panel_lblue_plain-64-baked/panel_peragent_supl_hlight.png: $(top_srcdir)/panel_lblue_plain-64/panel_peragent_supl_empty.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) "$<" -channel RGB -fuzz 100% -fill white -opaque black \
        -background black -alpha remove -bordercolor black -border 4x4 \
        -define convolve:scale='!' -morphology Convolve Laplacian:1 \
        -shave 4x4 -threshold 1% -fuzz 1% -transparent black \
        -channel R -evaluate multiply 0.00 \
        -channel G -evaluate multiply 0.99 \
        -channel B -evaluate multiply 0.99 \
        +channel -colorspace RGB "$@"

# Use ImageMagick to generate light teal highlight border sprites around weapon boxes
# The algorithm goes as explained before, but here the hole in the sprite is firs patched with empty weapon
# For each sprite, a shift required to fully patch the hole is a bit different
panel_lblue_plain-64-baked/panel_weapon_frame_hlight.png: $(top_srcdir)/panel_lblue_plain-64/panel_weapon_frame.png $(top_srcdir)/panel_lblue_plain-64/weapon_bk_empty.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) $+ -gravity Center -geometry -6+0 -composite \
	    -channel RGB -fuzz 100% -fill white -opaque black \
        -background black -alpha remove -bordercolor black -border 4x4 \
        -define convolve:scale='!' -morphology Convolve Laplacian:1 \
        -shave 4x4 -threshold 1% -fuzz 1% -transparent black \
        -channel R -evaluate multiply 0.00 \
        -channel G -evaluate multiply 0.99 \
        -channel B -evaluate multiply 0.99 \
        +channel -colorspace RGB "$@"

panel_lblue_plain-64-baked/panel_weapon_list_frst_hlight.png: $(top_srcdir)/panel_lblue_plain-64/panel_weapon_list_frst_frame.png $(top_srcdir)/panel_lblue_plain-64/weapon_bk_empty.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) $+ -gravity Center -geometry +6+4 -composite \
	    -channel RGB -fuzz 100% -fill white -opaque black \
        -background black -alpha remove -bordercolor black -border 4x4 \
        -define convolve:scale='!' -morphology Convolve Laplacian:1 \
        -shave 4x4 -threshold 1% -fuzz 1% -transparent black \
        -channel R -evaluate multiply 0.00 \
        -channel G -evaluate multiply 0.99 \
        -channel B -evaluate multiply 0.99 \
        +channel -colorspace RGB "$@"

panel_lblue_plain-64-baked/panel_weapon_list_next_hlight.png: $(top_srcdir)/panel_lblue_plain-64/panel_weapon_list_next_frame.png $(top_srcdir)/panel_lblue_plain-64/weapon_bk_empty.png
	$(MKDIR_P) "$(@D)"
	$(MAGICK_CONVERT) $+ -gravity Center -geometry +1+2 -composite \
	    -channel RGB -fuzz 100% -fill white -opaque black \
        -background black -alpha remove -bordercolor black -border 4x4 \
        -define convolve:scale='!' -morphology Convolve Laplacian:1 \
        -shave 4x4 -threshold 1% -fuzz 1% -transparent black \
        -channel R -evaluate multiply 0.00 \
        -channel G -evaluate multiply 0.99 \
        -channel B -evaluate multiply 0.99 \
        +channel -colorspace RGB "$@"

data/%.dat:
	$(MKDIR_P) "$(@D)"
	$(PNGTORAW) -b -o "$@" -p "$(word 2,$^)" -f sspr -l 0 "$<"

docs_DATA = README.md gfx_config.h
docsdir = $(prefix)/$(PARENT_PACKAGE)

EXTRA_DIST = gfxani docs mouse0 pointr0 font0 pop0

install-data-hook:
	cd "$(DESTDIR)${prefix}/$(PARENT_PACKAGE)"; \
	mv README.md gfx_readme.md
