
DRAFTS = \
	 4-bypass-pf-draft.pdf \
	 4-dokumentation-draft.pdf \
	 4-aktualisieren-draft.pdf \
	 4-zusaetzliche-software-draft.pdf \
	 A-risikoanalyse-draft.pdf \
#
PANDOCDIR = ../pandoc

%-draft.pdf: %.mdwn
	pandoc -o $@ -H $(PANDOCDIR)/draft.tex $<

all:

clean:
	rm -f *.pdf

drafts: $(DRAFTS)
