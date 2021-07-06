manuscript = dissertation
references = dissertation
latexopt   = -halt-on-error -file-line-error

all: all-via-pdf

quick: $(manuscript).tex
	pdflatex $(latexopt) $(manuscript)

all-via-pdf: $(manuscript).tex
	pdflatex $(latexopt) $(manuscript)
	makeglossaries $(manuscript)
	bibtex $(references)
	pdflatex $(latexopt) $(manuscript)
	pdflatex $(latexopt) $(manuscript)

all-via-dvi:
	latex $(latexopt) $(manuscript)
	#bibtex $(references).aux
	#latex $(latexopt) $(manuscript)
	#latex $(latexopt) $(manuscript)
	dvipdf $(manuscript)

diff:
	./diff.xsh --manuscript $(manuscript)-diff submitted

epub:
	latex $(latexopt) $(manuscript)
	bibtex $(manuscript).aux
	mk4ht htlatex $(manuscript).tex 'xhtml,charset=utf-8,pmathml' ' -cunihtf -utf8 -cvalidate'
	ebook-convert $(manuscript).html $(manuscript).epub

clean:
	rm -f $(manuscript).pdf *.dvi *.toc *.aux *.out *.log *.bbl *.blg *.log *.spl *~ *.spl *.zip *.acn *.glo *.ist *.epub *.idx *.lof *.lot

realclean: clean
	rm -rf $(manuscript).dvi
	rm -f $(manuscript).pdf

%.ps :%.eps
	convert $< $@

%.png :%.eps
	convert $< $@

zip:
	zip paper.zip *.tex *.eps *.bib

.PHONY: all clean
