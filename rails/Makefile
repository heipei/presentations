STYLES = $(shell echo *.sty)

.PHONY: all clean clean-misc clean-pdf

#all: vortrag-handout.pdf vortrag-folien.pdf
all: vortrag-handout.pdf

clean: clean-misc clean-pdf
clean-misc: clean-vortrag-folien-misc clean-vortrag-handout-misc
clean-pdf: clean-vortrag-folien-pdf clean-vortrag-handout-pdf

%.pdf: %.tex vortrag.tex img/* $(STYLES)
	test -f $*.toc || pdflatex $<
	pdflatex $<

clean-%-pdf:
	rm -f $*.pdf

clean-%-misc:
	rm -f $*.{aux,log,nav,out,snm,toc} missfont.log

