# PANDOC = pandoc -s --mathml 
PANDOC = pandoc -s --webtex 
MD0 = $(patsubst %.md0,%.md,$(wildcard *.md0))
# MD0 = $(wildcard *.md0)
HTML = $(patsubst %.md,%.html,$(wildcard *.md)) $(patsubst %.md0,%.html,$(wildcard *.md0))
MD   =  introduction.md html.md css.md javascript.md javascript_library.md dhtml.md node.md node_web.md node_form.md end.md appendix.md book.md exam.md tail.md 
PARG = -c ../css/book.css -B header.htm -A footer.htm --toc --base-header-level=1 --toc-depth=2 
PEPUB = --toc --base-header-level=1 --toc-depth=2 --epub-metadata=metadata.xml --epub-stylesheet=../css/book.css 
EARG = --margin-top=16 --margin-bottom=16 --margin-left=20 --margin-right=20 \
--pretty-print --base-font-size=9 --font-size-mapping="7, 8, 9, 12, 14, 16, 20, 24" 
RM = rm -f

.PHONY: all

all: $(HTML) shtm epubipad epubA4 pdfipad pdfA4 

epubA4: $(MD0)
	$(PANDOC) $(PEPUB) --epub-cover-image=../img/coverA4.jpg $(MD) -o ../book/A4.epub

pdfA4: epubA4
	ebook-convert ../book/A4.epub ../book/A4.pdf $(EARG) --paper-size=a4

epubipad: $(MD0)
	$(PANDOC) $(PEPUB) --epub-cover-image=../img/cover.jpg $(MD) -o ../book/ipad.epub

pdfipad: epubipad
	ebook-convert ../book/ipad.epub ../book/ipad.pdf $(EARG) --output-profile=ipad3
	
html: $(MD0) $(HTML)

shtm: 
	$(PANDOC) $(MD) -o ../book/book.html $(PARG)

md0: $(MD0)
    
%.md0 : 
	node md0.js $*.md0 $*.md
    
%.md: %.md0
	node md0.js $< $@

%.html: %.md
	$(PANDOC) $< reflink.md9 -o ../htm/$@ $(PARG)
	
clean: 
	${RM} ../htm/*.*
	${RM} ../book/*.*
	${RM} ../timg/*.*
	${RM} $(MD0)

    
# $?：代表已被更新的 dependencies 的值。也就是 dependencies 中，比 targets 還新的值。
# $@：代表 targets 的值。
# $<：代表第一個 dependencies 的值。
# $* : 代表 targets 所指定的檔案，但不包含副檔名。
