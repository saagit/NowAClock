These images are courtesy of [NASA's Scientific Visualization
Studio](https://svs.gsfc.nasa.gov/4404).  The NASA images accurately
represent phase, libration, diameter, etc. for every hour of each
year, but I only needed a set of 16 images representing the phases of
the moon.

I found a cycle where the full moon occurred right on the hour ([12:00
UTC on March 23,
2016](https://www.timeanddate.com/moon/phases/timezone/utc?year=2016))
which is frame 1981 of the 2016 animation.  The cycle was 29 days, 9
hours and 29 minutes long or 705.483 hours.  I wanted images for every
1/16 of the cycle (44.093 hours) so the following frames were used to
depict the phases:

|Fraction|Frame|Phase|
|-|-|-|
|0/16|1628|New Moon|
|1/16|1672||
|2/16|1716|Waxing crescent|
|3/16|1761||
|4/16|1805|First quarter|
|5/16|1849||
|6/16|1893|Waxing gibbous|
|7/16|1937||
|8/16|1981|Full Moon|
|9/16|2025||
|10/16|2069|Waning gibbous|
|11/16|2113||
|12/16|2157|Third quarter|
|13/16|2201||
|14/16|2246|Waning crescent|
|15/16|2290||

Only the higher resolution images from NASA have an alpha layer so the
`1920x1080 30.0 fps Frames: Plain` TIF images were used.  They were
then cropped to be square, resized to half size and saved as PNGs.
The entire process can be replicated using `make clean all`.  Finally,
the PNGs were checked in.
