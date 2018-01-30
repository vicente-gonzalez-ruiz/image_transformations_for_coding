include $(HOME)/Makefile_templates/05-tex2pdf/Makefile
include $(HOME)/Makefile_templates/10-fig2pdf/Makefile
include $(HOME)/Makefile_templates/20-pdf2svg/Makefile

lena.png:
	wget http://www.hpca.ual.es/~vruiz/images/lena.png

lena-gray.png:	lena.png
	convert -colorspace gray lena.png lena-gray.png

2D-DWT.svg:	2D-DWT.fig lena-gray.png lena.S*.png

orderers-and-scalabilities.svg:	progresion-LR.pdf progresion-RL.pdf

default: all

all:	$(TMPs)
