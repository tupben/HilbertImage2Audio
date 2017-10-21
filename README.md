# HilbertImage2Audio
Trying to turn images into audio


So far 1 file:


'convert' function takes a 2d numpy array and flattens it to a 1d numpy array. The order is determined by a hilbert curve snaking through the space. It works only on arrays of the shape (n**2, n**2) where n is natural number.


Next step: convert an image into an array of appropriate shape.
Decision: convert RGB / RGBA into luminocity vector? Or keep colors and proceed with 4 dimensions. Are there enough dimensions in the audio to account for this?


Final step: convert a list of values to an audio file. Libraries?
For a BW image, the Hilbert curve has 2 dim: begining/end and bright/dark. These are mapped to audio:

low pitches   <-> beginning of the curve

high pitches  <-> end of the curve

bright pixels <-> high-amplitude (loud)

dark pixels   <-> low-amplitude (quiet)


To make it more consonant, maybe round to the nearest piano pitch?
Mapping doesn't have to be linear. Octaves, consonances, dissonances will create an uninteded effect.
