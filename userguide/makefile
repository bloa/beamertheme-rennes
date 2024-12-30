SLIDES=main
BG=bg_title
SLIDES_TEX=$(addsuffix .tex,$(SLIDES))
SLIDES_PDF=$(addsuffix .pdf,$(SLIDES))
BG_TEX=$(addsuffix .tex,$(BG))
BG_PDF=$(addsuffix .pdf,$(BG))

all: ${BG_PDF} ${SLIDES_PDF}

$(BG_PDF): %.pdf: %.tex bg_preamble.tex
	pdflatex \\nonstopmode \\input{$<}

$(SLIDES_PDF): %.pdf: %.tex preamble.tex $(BG_PDF)
	pdflatex \\nonstopmode \\input{$<}

clean:
	rubber $(BG_TEX) $(SLIDES_TEX) --clean
