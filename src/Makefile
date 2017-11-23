all: yaguitar-plain.pdf yaguitar-latex.pdf

yaguitar-plain.pdf: *.tex *.sty
	pdfcsplain yaguitar-plain.tex && rm -rf *.log *.aux

yaguitar-latex.pdf: *.tex *.sty
	pdflatex yaguitar-latex.tex && rm -rf *.log *.aux

clean:
	/bin/rm -f *.pdf *~
