
DRAFTS = 1-ich-will-den-openwrt-paketfilter-verstehen-draft.pdf \
         2-aufgaben-eines-paketfilters-draft.pdf \
         2-welche-protokolle-draft.pdf \
	 2-ipv4-fuer-firewall-draft.pdf \
	 2-ipv6-fuer-firewall-draft.pdf \
	 3-netfilter-kernel-draft.pdf \
	 3-openwrt-luci-draft.pdf \
#
PANDOCDIR = ../pandoc

%-draft.pdf: %.mdwn
	pandoc -o $@ -H $(PANDOCDIR)/draft.tex $<

all:

clean:
	rm -f *.pdf

drafts: $(DRAFTS)
