## Process this file with automake to produce Makefile.in

bin_PROGRAMS = file-apng

bindir = $(GIMP_LIBDIR)/plug-ins

file_apng_SOURCES = \
	plugin-intl.h	\
	file-apng.c

file_apng_CPPFLAGS = \
	-DLOCALEDIR=\""$(LOCALEDIR)"\"		\
	-DDATADIR=\""$(DATADIR)"\"

INCLUDES =\
	-I$(top_srcdir)		\
	@GIMP_CFLAGS@		\
	-I$(includedir)

LDADD = $(GIMP_LIBS)

