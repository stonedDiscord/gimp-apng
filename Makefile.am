#

SUBDIRS = po src ui help

EXTRA_DIST = \
	BUGS			\
	HACKING			\
	autogen.sh		\
        intltool-extract.in	\
        intltool-merge.in	\
        intltool-update.in

DISTCLEANFILES = \
	intltool-extract	\
	intltool-merge		\
	intltool-update

# ChangeLog generation

ChangeLog: $(srcdir)/ChangeLog
$(srcdir)/ChangeLog:
	@echo Creating $@ based on git log
	@if test -d "$(srcdir)/.git"; then \
	  (GIT_DIR=$(top_srcdir)/.git $(srcdir)/config/missing --run \
	   git log --stat) | fmt --split-only > $@.tmp \
	  && mv -f $@.tmp $@ \
	  || ($(RM) $@.tmp; \
	      echo Failed to generate ChangeLog, your ChangeLog may be outdated >&2; \
	      (test -f $@ || echo git-log is required to generate this file >> $@)); \
	else \
	  test -f $@ || \
	  (echo A git checkout and git-log is required to generate ChangeLog >&2 && \
	  echo A git checkout and git-log is required to generate this file >> $@); \
	fi
.PHONY: ChangeLog $(srcdir)/ChangeLog
