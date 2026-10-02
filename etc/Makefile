include ../defines.mk

UNITS := pve-lxc-syscalld.service
# for the pkg.pve-lxc-syscalld.lsbservice build profile, see debian/rules
INIT_SCRIPTS := pve-lxc-syscalld.init

all: $(UNITS) $(INIT_SCRIPTS)

clean:
	rm -f $(UNITS) $(INIT_SCRIPTS)

.SUFFIXES: .service.in .service .init.in .init
.service.in.service .init.in.init:
	sed \
	    -e 's!%LIBEXECDIR%!$(LIBEXECDIR)!g' \
	    $< >$@.tmp
	mv $@.tmp $@
