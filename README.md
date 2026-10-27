# iFNEK

Interactive Fundamental Nuclear Engineering Knowledge

General workflow to create it:
Import the pdf image as an svg and add named boxes to it in inkscape, which are invisible but callable by html.
The main page is the index.html (static website). It loads FNEK.svg and content.json and makes every box listed in content.json clickable.
Each entry in content.json is keyed by the box id and holds the popup HTML (`body`) and an orientation (left, middle or right) based on position in the pdf.
Then when you click on a box, it shows that entry's HTML in the little callout. Popup styles (e.g. `.card`, `.concept`) live in index.html.

To add a new item:
1. Draw a box over it in inkscape and give it a unique id.
2. Add an entry with the same `id` to content.json.

The svg is minified for size (svgo, keeping all ids), and images no longer drawn on the card were removed from it. The original inkscape file is in the git history before the minification commit. If you re-export the card, check the file size.

The popup engine is `irdc.js` (with `irdc.css`). Both files are identical in all four card repos (iRDC300, iRDC450, iFNEK, iFNEK_C): make a change in one and copy the file unchanged to the other three. Each index.html only sets the card's SVG and data file names (`window.IRDC = { svg: ..., data: ... }`) and any card-specific popup styles.
Hotspots can be reached with Tab and opened with Enter; Esc or a click outside closes the popup. On phones the card scrolls sideways at full size and the popup appears along the bottom of the screen.
