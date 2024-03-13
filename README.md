# BAWicons
A collection of SVG icons for Home Assistant in a .js file suitable for execution

These are icons I've created for personal use.  They started as a small enhancement of
hass-bha-icons, a similar collection from github user 'hulkhaugen'.  This author is indebted to the
availability of this prior work as a how-to guide.  (I'm a lifetime software and firmware
programmer, but a relative novice in all things HA-related.)

________
ADDITIONAL ICONS

At the time of initial release, this library contains (43) 24x24 pixel SVG-based icons.  The mix is
somewhat eclectic, and heavily music-based because, well, I'm a musician.  The MDI icon list is
huge, but it doesn't have many icons specific to music and audio -- so I fixed that.  Some readers
may find the library highly useful; others may think it's all a bunch of nonsense.  YMMV.

If you enjoy programming and drawing icons, this is a great start for you.  Instructions to modify
and install your library are shown below.

If you don't program and can't draw/modify existing icon files, feel free to suggest updates to
this library.  I make no promise that I will add them, though.  I am retired and this programming
is something of a hobby:

  * The more HA users who request a particular icon, the more likely that I will create it.  That said,
    continually asking me to make your favorite icon will *not* improve the odds; in fact, it may have the opposite effect.

  * If the icon is a small modification to one of my existing icons, I will probably add it.

  * If I find a particular suggestion useful for my own needs, it will improve the priority of that icon.

  * I won't likely make more than one content-based release per month.

________
MODIFYING THE LIBRARY

Users are encouraged to hack and modify this library to meet personal needs.  If you release the
results of your work, I ask that you credit both hulkhaugen and myself (drawbars37) as sources,
as well as any other icon source used as a starting point for new icons.

The overall structure of the library is a .js file with an array called 'BAW_ICONS_MAP' -- which
can be changed if you create a new library -- containing a series of elements:

  * Each element should be based on a single-path 2-color SVG file of native size 24x24 pixels.  Files
    with a larger native size will often work, but will result in tiny icons that need to be artificially
    expanded in Lovelace UIs; sometimes, the required expansion will have unwanted effects.

  * The first line of the element contains the icon name in double-quotes, followed by a colon.

  * The second line contains the path from the corresponding SVG file, stripped of any extra characters
    not contained between the two double-quotes.

  * The second line of every element *except the last one* should end with a comma.

There are some other items near the bottom of the .js file that need to be changed:

  * The iconsetHTML array name, BAW_ICONS_MAP, can be changed, but care should be taken to replace all
    instances of the name.

  * The iconset.name is "baw".  If you create your own library, this name can be changed.

  * The iconset.size should be updated to match the number of icons in the library.

________
INSTALLING THE LIBRARY

The .js file must be copied to the www directory of the Home Assistant client that executes HASS
(Raspberry Pi, x64, etc.).

The configuration.yaml file must be modified to point to the .js file with the icons.  If your
file doesn't already have a section called ```frontend:``` then create it:

```
frontend:
  extra_module_url:
    - /local/hass-baw-icons.js
```

If you plan to use more than one icon library, add it/them in this section.

________
USING THE LIBRARY

These icons can be used in a similar manner to the MDI set that are native to Home Assistant, substituting 'baw' for 'mdi' in the name:

```
icon: mdi:gauge

icon: baw:sports-car
```

