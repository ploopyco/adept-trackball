## Only one file? Where are the parts?

The STEP file contains all of the Adept trackball plastic parts in one file. Doing it this way preserves the assembly information, showing how the parts are supposed to fit together, as well as the expected clearances between parts. It also bundles all of the parts for a given revision together, so there's no accidental mixing of parts from different revisions.

## Where are the STLs?

There aren't any. STL files are to 3D models like compiled binaries are to code: useful, but not meaningfully open source. STEPs are editable and preserve design intent, which is why we're using them here.

## How do I print this?

You'll need to split the parts in the file up before you can print them. Most slicers can do this; if you have a compatible printer we recommend PrusaSlic3r, since that's the one we use in-house and have checked.

Note that submitting this file to some 3rd party print services will cause confusion, as they are expecting one body instead of many. To do this, you can use PrusaSlic3r to split the parts and then export each separately as an STL.