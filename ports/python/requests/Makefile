include ../../../mk/pitchfork.mk

# Local variables
_VER    = 2.7.0
_NAME   = requests-$(_VER)
_WRKSRC = $(WORKDIR)/$(_NAME)

# Local works
do-install: | $(PREFIX)/var/pkg/$(_NAME)
$(PREFIX)/var/pkg/$(_NAME):
	rm -rf $(STAGING)/$(_NAME)
	mkdir -p $(STAGING)/$(_NAME)
	$(PIP) install --root $(STAGING)/$(_NAME) --no-deps requests==$(_VER)
	rsync -aKx $(STAGING)/$(_NAME)/$(PREFIX)/ $(PREFIX)/
	cd $(STAGING)/$(_NAME)$(PREFIX) && find * |grep -v '^$$'|sort -r > $@
do-clean:
	rm -rf $(STAGING)/$(_NAME)
