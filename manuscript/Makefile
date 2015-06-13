
DRAFTS = 1-ich-will-den-openwrt-paketfilter-verstehen-draft.pdf \
         2-aufgaben-eines-paketfilters-draft.pdf \
	 2-wie-weit-draft.pdf
#
PANDOCDIR = ../pandoc

%-draft.pdf: %.mdwn
	pandoc -o $@ -H $(PANDOCDIR)/draft.tex $<

all:

clean:
	rm -f *.pdf

drafts: $(DRAFTS)
