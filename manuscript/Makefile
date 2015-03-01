
DRAFTS = ich-will-den-openwrt-paketfilter-verstehen-draft.pdf
#
PANDOCDIR = ../pandoc

%-draft.pdf: %.md
	pandoc -o $@ -H $(PANDOCDIR)/draft.tex $<

all:

drafts: $(DRAFTS)
