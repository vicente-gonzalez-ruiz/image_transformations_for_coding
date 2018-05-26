include $(HOME)/Makefile_templates/05-tex2pdf/Makefile
include $(HOME)/Makefile_templates/10-fig2pdf/Makefile
include $(HOME)/Makefile_templates/20-pdf2svg/Makefile

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

orderers-and-scalabilities.pdf:	progresion-LR.pdf progresion-RL.pdf

default: all

all:	$(TMPs)
