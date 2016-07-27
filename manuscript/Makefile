
DRAFTS = \
	 2-nat-draft.pdf \
	 4-bypass-pf-draft.pdf \
	 4-monitoring-draft.pdf \
	 4-dokumentation-draft.pdf \
	 A-analyse-iptables-draft.pdf \
	 A-risikoanalyse-draft.pdf \
#
PANDOCDIR = ../pandoc

%-draft.pdf: %.mdwn
	pandoc -o $@ -H $(PANDOCDIR)/draft.tex $<

all:

clean:
	rm -f *.pdf

drafts: $(DRAFTS)
