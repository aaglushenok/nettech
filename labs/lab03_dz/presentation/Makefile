PRESENTATION = presentation.md
FILTERS = --filter pandoc-crossref --citeproc
OPTIONS = --number-sections
PDF_ENGINE = --pdf-engine=xelatex
REVEALJS = /home/aaglushenok/reveal.js

all: presentation.pdf presentation.html presentation.qmd

presentation.pdf: $(PRESENTATION)
	pandoc "$(PRESENTATION)" $(FILTERS) $(PDF_ENGINE) $(OPTIONS) -t beamer --slide-level=2 -o presentation.pdf

presentation.html: $(PRESENTATION)
	pandoc "$(PRESENTATION)" --embed-resources --standalone -t revealjs -V theme=beige -V revealjs-url=$(REVEALJS) $(FILTERS) -o presentation.html

presentation.qmd: $(PRESENTATION)
	pandoc "$(PRESENTATION)" $(FILTERS) $(OPTIONS) -t markdown -o presentation.qmd

clean:
	rm -f presentation.pdf presentation.html presentation.qmd

.PHONY: all clean
