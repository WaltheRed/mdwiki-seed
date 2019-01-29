# ImageMagick

[usage](http://www.imagemagick.org/Usage/)

To achieve faster execution:
1. Disable HDRI (halves the memory usage): ```./configure --disable-hdri``` [more](https://imagemagick.org/script/high-dynamic-range.php)
2. Use/Build Q8 non-HDRI version of the software (halves the memory usage again)

## Montage

[usage](http://www.imagemagick.org/Usage/montage/)

Be careful with the additional options! It can quickly become very slow.

    montage input/* output.png

Resize & add a space between the images with ```-geometry <Size-X>x<Size-Y>+<Space-Vertical>+<Space-Horizontal>```. More options are available! :)

Change the tiling with ```-tile <X>x<Y>```. Remove a dimension to remove the restriction otherwise given.

Add a shadow with ```-shadow```. \*duh\*

Again, more options are available! :)