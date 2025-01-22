#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.
AC_PREREQ([2.69])

m4_define([ver_major], [1])
m4_define([ver_minor], [0])
m4_define([ver_release], [3])
# Set build number to commit count only if ".git" folder is present
m4_define([ver_build], m4_if(m4_esyscmd_s([ls -1 -d ".git" 2>&1]),.git,[m4_esyscmd_s([git rev-list --count HEAD])],[0]))

m4_define([swars_gfx_version],
      [ver_major.ver_minor.ver_release.ver_build])

AC_INIT([Syndicate Wars GFX], [swars_gfx_version], [mefistotelis@gmail.com], [swars_gfx])

m4_define([parent_package], [swars])
AC_DEFINE([PARENT_PACKAGE], [parent_package], [Name of the parent package, for which this one provides data files])

AC_CONFIG_SRCDIR([data/nfra-0.ani])
# We use header file as means to transfer properties to automation scripts
AC_CONFIG_HEADERS([gfxprivconfig.h])
AX_PREFIX_CONFIG_H([gfx_config.h], [GFX])
AC_CONFIG_MACRO_DIRS([m4])

AC_CANONICAL_HOST
AC_CANONICAL_TARGET

AM_INIT_AUTOMAKE([foreign])
ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

# Checks for programs
PKG_PROG_PKG_CONFIG
AC_PROG_MKDIR_P

AC_CHECK_PROGS(MAGICK_CONVERT, [$MAGICK magick convert], [magick-notfound],
  [${PATH}${PATH_SEPARATOR}/usr/local/bin${PATH_SEPARATOR}${srcdir}/bin])
AS_VAR_IF([MAGICK_CONVERT], [magick-notfound],
  [AC_MSG_ERROR([Tool imagemagick not found in bin dir or PATH dirs. Install it before configuring.])], [])
AS_VAR_IF([MAGICK_CONVERT], [magick], [AS_VAR_APPEND([MAGICK_CONVERT], [" convert"])], [])

AC_CHECK_PROGS(MAGICK_MONTAGE, [$MAGICK magick montage], [magick-notfound],
  [${PATH}${PATH_SEPARATOR}/usr/local/bin${PATH_SEPARATOR}${srcdir}/bin])
AS_VAR_IF([MAGICK_MONTAGE], [magick-notfound],
  [AC_MSG_ERROR([Tool imagemagick not found in bin dir or PATH dirs. Install it before configuring.])], [])
AS_VAR_IF([MAGICK_MONTAGE], [magick], [AS_VAR_APPEND([MAGICK_MONTAGE], [" montage"])], [])

AC_PATH_PROG([PNGTORAW], [pngpal2raw], [pngpal2raw-notfound],
  [${PATH}${PATH_SEPARATOR}/usr/local/bin${PATH_SEPARATOR}${srcdir}/bin])
AS_VAR_IF([PNGTORAW], [pngpal2raw-notfound],
  [AC_MSG_ERROR([Tool pngpal2raw not found in bin dir or PATH dirs.])], [])

# Default install dir
#AC_PREFIX_DEFAULT(/usr/local)

# Flags
AC_SUBST([PARENT_PACKAGE], [parent_package])

# Prepare makefiles from `.in` templates
AC_CONFIG_FILES([Makefile])

# Done - generate and execute `config.status`
AC_OUTPUT
