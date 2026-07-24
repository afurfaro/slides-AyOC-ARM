export LC_ALL=C

TEX=ComputerOrganization-Intro.tex
PDF=ComputerOrganization-Intro

### Don't touch beyond this point.

PDF_N=$(PDF).pdf
PDF_H=$(PDF)-handout.pdf
OUTPUT=$(PDF_N) $(PDF_H)

# LaTeX flags
TEXFLAGS=-file-line-error -interaction=nonstopmode

#slides: $(PDF_N)

all: $(PDF_N) $(PDF_H)

handout: $(PDF_H)

$(PDF_N): $(TEX) Makefile
	make -C ../img/
	pdflatex $(TEXFLAGS) -jobname $(PDF) $<

$(PDF_H): $(TEX)
	echo '\PassOptionsToClass{handout}{beamer}\input{$<}' | pdflatex $(TEXFLAGS) -jobname $(PDF)-handout 

clean:
	rm -f *.gz *.aux *.log *.out *.toc *.nav *.snm *.vrb $(PDF).pdf $(PDF)-handout.pdf
