html:
	scholdoc webpage-settings.yml dolphins.md --citeproc --output=dolphins.html

latex:
	scholdoc plos-one-settings.yml dolphins.md --natbib --output=dolphins.tex

# Need the `latexmk` program to automate LaTeX builds (included with texlive)
pdf: latex
	latexmk -pdf dolphins.tex

# Scholdoc native PDF output doesn't call bibtex
autopdf:
	scholdoc plos-one-settings.yml dolphins.md --citeproc --to=latex --output=dolphins_generatedByScholdoc.pdf

clean:
	-[[ -f "dolphins.aux" ]] && latexmk -c
	-[[ -f "dolphins.tex" ]] && rm dolphins.tex
	-[[ -f "dolphins.bbl" ]] && rm dolphins.bbl
	-[[ -f "dolphins.pdf" ]] && rm dolphins.pdf
	-[[ -f "dolphins.html" ]] && rm dolphins.html

.PHONY: html latex pdf autopdf clean
