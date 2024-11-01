#
#
#         Name: makefile (rules file for 'make')
#         Date: 2024-10-30 (Wed)
#
#
#

APPLID          =       vmlink
VERSION         =       2.1
PREFIX          =       /

.PHONY: install clean distclean

_default:
	@echo "$(MAKE): specify something to make!"
	@false

install:
	mkdir -p $(PREFIX) $(PREFIX)/etc $(PREFIX)/etc/sysconfig
	cp -p ../etc/auto.vmlink $(PREFIX)/etc/.
	cp -p ../etc/sysconfig/vmlink $(PREFIX)/etc/sysconfig/.

vmlink.rpm:
	./rpmbuild.sh $(APPLID) $(VERSION)

clean:
	rm -f *.rpm *.log vmlink.spec

distclean:
	@$(MAKE) clean
	rm -f .rpmseq


