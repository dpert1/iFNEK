# iFNEK

Interactive Fundamental Nuclear Engineering Knowledge

General workflow to create it:
Import the pdf image as an svg and add named boxes to it in inkscape, which are invisible but callable by html.
The main page is the index.html (static website) which creates the clickable areas you drew in step 1 by their name you used in step 1.
Those clickable areas call the FNEK description and an orientation (left right middle) based on position in the pdf.
Then when you click on a box, it makes the little callout from the FNEK description html.

