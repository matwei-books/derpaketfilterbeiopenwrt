
PANDOCDIR = ../pandoc

%-draft.pdf: %.md
	pandoc -o $@ -H $(PANDOCDIR)/draft.tex $<

%-draft.pdf: %.otl
	../bin/otl2markdown $< \
	| pandoc -o $@ -f markdown -H $(PANDOCDIR)/draft.tex
