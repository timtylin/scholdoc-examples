html:
	scholdoc webpage-settings.yml dolphins.md --citeproc --output=dolphins.tex

latex:
	scholdoc plos-one-settings.yml dolphins.md --natbib --output=dolphins.tex

# Need the `latexmk` program to automate LaTeX builds (included with texlive)
pdf: latex
	latexmk -pdf dolphins.tex

# Scholdoc native PDF output doesn't call bibtex
autopdf:
	scholdoc plos-one-settings.yml dolphins.md --citeproc --to=latex --output=dolphins.pdf

clean:
	latexmk -c
	rm dolphins.tex
	rm dolphins.bbl
	rm dolphins.pdf
	rm dolphins.html

.PHONY: html latex pdf autopdf clean
