# cpidisplay
IDL based display program for SPEC Inc's Cloud Particle Imager (CPI).

cpidisplay.pro is the main program.  It creates the window and all of the
widgets in the window.

cpiread.pro does all the file functions.  It reads the raw cpi data file.

scale.gif is the gif image that contains the scale arrow that is displayed in
the program.  It shows the scale of the cpi images.

cpidisplay.sav is the idl save file that has the *.pro files saved in it.
You must keep the cpidisplay.sav program in a different directory from the
.pro files, otherwise idl will read the .pro files before it will read the
.sav file.  Create a new save file when there is a new release of
the programs.

To run the program, cd to the directory where the cpidisplay.sav file resides,
which should not have the .pro files in it.
Then run idl, then type cpidisplay at the idl prompt.

To run the program without using the save file, cd to the directory where the
.pro files reside.  Then run idl, then type the following commands at the idl
prompt:
.compile cpidisplay
.compile cpiread
cpidisplay

You will need to change the programs in a few places.  In cpidisplay.pro,
line 97 contains the main data directory where the raw cpi data resides.
line 126 contains the directory where the scale.gif image resides.  In
cpiread.pro, line 204 contains the directory where the gif images that are
created are placed.

cpi is the program that users can run to put them in the directory where the
cpidisplay.sav file resides.  It also starts idl for them, then they just have
to enter cpidisplay to run the program.

To create the cpidisplay.sav program, cd to the directory where the .pro files
reside.  Start idl, then type the following commands:
.compile cpidisplay
.compile cpiread
resolve_all
save, /routines, filename="cpidisplay.sav"

Run
idl -vm="cpidisplay.sav"
to test the .sav file in the virtual machine environment.

Copy the cpidisplay.sav file to ftp://ftp.eol.ucar.edu/pub/archive/RAF-src/cpidisplay.sav

The download page for the cpidisplay program is located at
http://www.eol.ucar.edu/raf/ION/html/cpidata.html
