# Makefile para report_main.tex SEM BibTeX

TEX=pdflatex -interaction=nonstopmode -halt-on-error
MAIN=report_main
BUILDDIR=build

all: $(BUILDDIR)/$(MAIN).pdf

# 1ª passada: gera .aux e .toc
$(BUILDDIR)/$(MAIN).toc: $(MAIN).tex | $(BUILDDIR)
	$(TEX) -output-directory=$(BUILDDIR) $(MAIN).tex

# 2ª passada: lê .toc e monta o sumário
$(BUILDDIR)/$(MAIN).pdf: $(MAIN).tex $(BUILDDIR)/$(MAIN).toc
	$(TEX) -output-directory=$(BUILDDIR) $(MAIN).tex

$(BUILDDIR):
	mkdir -p $(BUILDDIR)

clean:
	rm -f $(BUILDDIR)/*.aux $(BUILDDIR)/*.bbl $(BUILDDIR)/*.blg $(BUILDDIR)/*.log \
	      $(BUILDDIR)/*.nav $(BUILDDIR)/*.out $(BUILDDIR)/*.snm $(BUILDDIR)/*.toc \
	      $(BUILDDIR)/*.vrb $(BUILDDIR)/*.brf $(BUILDDIR)/*.lof $(BUILDDIR)/*.lot \
	      $(BUILDDIR)/*.fls $(BUILDDIR)/*.fdb_latexmk $(BUILDDIR)/*.pdf

.PHONY: all clean
.PRECIOUS: $(BUILDDIR)/$(MAIN).pdf $(BUILDDIR)/$(MAIN).toc
