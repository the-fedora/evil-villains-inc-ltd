# Introduction #

README


# Details #

The R code contained in fresnel.r and fresnlib.r computes parameters for a fresnel reflector given a footprint (horizontal space available), a focal radius (how tightly should the reflector focus) and a focal length.

Currently, main() ouputs an R table with parameters for constructing the reflector by cutting out circular segments from a base material, removing an angular segment, and reattaching the ends, giving a bevel of the necessary computed angle.  It may be necessary on some systems to reassign HEADER to colnames(RESULTS) before printing RESULTS again, to ensure correct labeling.  Alternatively, one may simply consult the HEADER without assigning it to RESULTS, to keep a more compact format.

USAGE
Doomray requires R (r-project.org) to run.

Edit fresnel.r so that LIBPATH points to where you have placed fresnlib.r (Normally in the same directory you placed fresnel.r).  Run R, then type:
> source("/PATH/TO/fresnel.r")
To create a reflector, run
> main(Footprint,r,FL)
If you don't know what that means, run
> usage()

Flat Radius (c) is the radius of the inside of the circle to transcribe on your base material.  Ring width is the amount to add for the outer radius of the ring.  Deg. Cutout is the degrees of ring to remove to create a bevel, and Inner Radius is the inside radius of the beveled ring once it is glued back together.  To construct reflector:

Using a compass, draw the inner radius (Flat Radius (c)) of the first ring on your base material, then draw the outer radius by adding Ring Width to the flat radius.  Repeat for as many rings as you wish to use (often, the last ring will be very small and unlikely to add much).  Before cutting out the ring, use a straight edge and protractor to mark the indicated cutout (Deg. Cutout).  You may wish to use the cutout to make tabs to assist in construction.  Now you can cut the ring out of the base material, remove the cutout, and reaffix the two ends together to create a beveled ring.  If necessary, cover with reflective material, then repeat for the remainder of the rings, and affix them concentrically on a flat platform, this will be easier if you scribe the inner radii with your compass to aid in placement.

output(FILENAME) writes out two files, FILENAME.csv and FILENAME.scad, where FILENAME is whatever you choose (there is no default).  FILENAME.csv is a csv table with the output obtained by running main(), and can be opened with any major office spreadsheet program.  FILENAME.scad is a SCAD-format 3D representation of the reflector, which can be viewed and edited with OpenSCAD and possibly other software, and is suitable for 3D printing, though you may need to adjust the fineness level manually first.