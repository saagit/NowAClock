PNGS := moon00.png moon01.png moon02.png moon03.png \
	moon04.png moon05.png moon06.png moon07.png \
	moon08.png moon09.png moon10.png moon11.png \
	moon12.png moon13.png moon14.png moon15.png

TIFS := $(PNGS:.png=.tif)


# The source of the original images
NASA_SITE := https://svs.gsfc.nasa.gov
NASA_PATH := vis/a000000/a004400/a004404/frames/1920x1080_16x9_30p/plain
# The actual images used for each phase
moon00src := moon.1628.tif
moon01src := moon.1672.tif
moon02src := moon.1716.tif
moon03src := moon.1761.tif
moon04src := moon.1805.tif
moon05src := moon.1849.tif
moon06src := moon.1893.tif
moon07src := moon.1937.tif
moon08src := moon.1981.tif
moon09src := moon.2025.tif
moon10src := moon.2069.tif
moon11src := moon.2113.tif
moon12src := moon.2157.tif
moon13src := moon.2201.tif
moon14src := moon.2246.tif
moon15src := moon.2290.tif

%.tif :
	wget -O $@ ${NASA_SITE}/${NASA_PATH}/${$*src}

%.png : %.tif
	convert $< \
	  -set option:distort:viewport "%[fx:min(w,h)]x%[fx:min(w,h)]+%[fx:max((w-h)/2,0)]+%[fx:max((h-w)/2,0)]" \
	  -filter point -distort SRT 0 +repage \
	  -resize 50% +repage $@

all : ${PNGS}

.PRECIOUS : ${TIFS}

.PHONY : cleanall clean clean_pngs

cleanall : clean clean_pngs

clean :
	rm -f ${TIFS}

clean_pngs :
	rm -f ${PNGS}
