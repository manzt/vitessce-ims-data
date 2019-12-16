# vitessce-ims-data
a repo for cataloging ideas around integrating spatial mass spec with vitessce

## viewer objectives
### high priority
- Support 2D spatial layers.
  - MxIF imaging channel (high resolution; OME-TIFF format)
  - IMS channel (annotated m/z ratio; currently in imzML format or .csv)
  - Segmentation polygons (in-house text format, should standardize)
  
- Support multiple layers and blending of 2D layers.

- Support a m/z spectrum view. Selection from IMS 2D spatial layer allows user to view entire m/z spectrum for point selection (or aggregate spectrum of multiple points).

### medium priority
- Support spatial selection (through segmentation or manual area selection) and aggregate underlying spectra (e.g. mean spectrum).

### lower priority
- For annotated m/z ratios, provide visual indication of confidence of annotation.

- Provide optional (toggle) view of QC summary for current IMS (data pending).

## priority interactions
- Selecting layers (via brush or annotation)
  - If annotated m/z (spase spectrum), fetch 2d slice at single m/z and render.
  - If raw data (dense spectrum), sample a few m/z in range initially and then load rest?
  - `NOTE`: The visual encoding for this selection should likely be dynamic (ie. spectrum for dense/raw data and table/heatmap/etc for annotated layers).

- Pan-and-zoom of rendered layers
  - Hopefully handled by deck.gl.

- Coordination between separate views
  - Look at current implementation linking 2D-Scatterplots in vitessce. 

## slower interactions
- Aggregate 2d spatial annotated m/z channels (ie. biologically meaningful grouping; m/z may be far apart)
  - likely some type of dropdown to select multiple annotated m/z.
  
- Create aggregate spectrum from 2d selection.

