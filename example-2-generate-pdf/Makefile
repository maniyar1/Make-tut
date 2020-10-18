# https://www.gnu.org/software/make/manual/make.html#Using-Variables

# Recursive variables
mark = cmark
# Can't do 
# mark = $(mark) {whatever}

# Simply expanded variables
pdfmark ::= $(mark) -t latex
mark ::= $(mark) -t latex # cmark -t latex
# pdfmark is still cmark -t latex
latex = pdflatex

hello-world.pdf: hello-world.tex
	$(latex) $(^)

hello-world.tex: hello-world.md
	printf "\documentclass[letter]{article} \n\\\begin{document} \n" > $(@)
	$(pdfmark) $(^) >> $(@)
	printf "\\\end{document}" >> $(@)

clean:
	rm -f hello-world.tex hello-world.pdf hello-world.aux hello-world.log
