TOPACK= ausarb.tex hsrmlogo.sty blindtext.sty ausarb.bib online.bib \
	zeichnung.odg zeichnung.pdf \
        Makefile latexank.tex 

all: ausarb.pdf latexank.pdf LaTeXBsp.zip

LaTeXBsp.zip: $(TOPACK)
	-/bin/rm -r LaTeXBsp
	mkdir LaTeXBsp
	cp $(TOPACK) LaTeXBsp
	zip -r LaTeXBsp.zip LaTeXBsp

# die Ausarbeitung mal mit pdflatex

ausarb.pdf: ausarb.tex
	pdflatex -interaction=nonstopmode ausarb.tex
	bibtex ausarb1
	bibtex ausarb2
	pdflatex -interaction=nonstopmode ausarb.tex # texen mit neuen Referenzen
	pdflatex -interaction=nonstopmode ausarb.tex # Jetzt spätestens sollte alles stimmen

# die Ankündigung mal normal und richtig
latexank.pdf: latexank.tex
	pdflatex -interaction=nonstopmode latexank.tex
	pdflatex -interaction=nonstopmode latexank.tex # beim zeiten Mal ist alles klar

clean:
	-/bin/rm ausarb.pdf latexank.pdf *.lof *.log *.lot *.aux *.bbl *.toc *.blg
