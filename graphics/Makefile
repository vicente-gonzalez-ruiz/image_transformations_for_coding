include $(HOME)/Makefile_templates/Makefile
#include $(HOME)/Makefile_templates/tex2pdf_rule/Makefile
#include $(HOME)/Makefile_templates/fig2pdf/Makefile
#include $(HOME)/Makefile_templates/pdf2svg/Makefile
#include $(HOME)/Makefile_templates/pdf2png_rule/Makefile

lena.png:
	wget http://www.hpca.ual.es/~vruiz/images/lena.png
TMPs += lena.png

lena-gray.png:	lena.png
	convert -colorspace gray lena.png lena-gray.png
TMPs += lena-gray.png

lena.ppm:	lena.png
	convert lena.png lena.ppm
TMPs += lena.ppm

lena-cut.png:	lena.ppm
		pnmcut -top 250 -right 350 -width 40 -height 40 < $< | pnmtopng > $@
TMPs += lena-cut.png

correlacion_lena.eps:	correlacion_lena.fig lena.png lena-cut.png
TMPs += correlacion_lena.pdf

2D-DWT.svg:	2D-DWT.fig lena-gray.png lena.S*.png

orderers-and-scalabilities.pdf:	progresion-LR.pdf progresion-RL.pdf orderers-and-scalabilities.tex

orderers-and-scalabilities.svg:	orderers-and-scalabilities.pdf
TMPs += orderers-and-scalabilities.svg

bit-plane-trans.pdf:	lena_plano* lena_rec* bit-plane-trans.tex

#bit-plane-trans.png:	bit-plane-trans.pdf
#TMPs += bit-plane-trans.png

default: all

all:	$(TMPs)
