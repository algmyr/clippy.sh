# clippy - a simple clipboard helper
A simple clipboard helper script. Makes it easy to list what
is stored in your clipboards and allows reading from/writing
to specific targets on the clipboards.

On top of that some quality of life features are included for
capturing screen to a clipboard.

## Examples

    $ clippy list
    TIMESTAMP
    TARGETS
    MULTIPLE
    SAVE_TARGETS
    text/html
    text/_moz_htmlinfo
    text/_moz_htmlcontext
    image/png
    image/bmp
    ...
    text/ico
    image/jpeg
    image/tiff
    $ clippy get image/png | image-viewer -
    
![image on clipboard](https://avatars2.githubusercontent.com/u/15268706?s=100&v=4)

    $ convert img.ppm png:- | clippy set image/png
    $ clippy list
    TARGETS
    image/png
    $ echo 'This combines nicely with pipes!' | clippy set
    $ echo 'Works well with primary selection too' | clippy -p set
    $ clippy get
    This combines nicely with pipes!
    $ clippy get -p
    Works well with primary selection too
    
### Unique prefix
    $ clippy screen_capture
    $ clippy scr
    $ clippy s
    No unique match, potential matches:
    set
    screen_capture
    $ clippy sett
    No matching action
    
    Usage: clippy [-bps] list/get/set/region_capture/screen_capture [target]
