mat2d3 -- a Matlab toolkit for generating d3.js visualizations
==============================================================

syntax
------
	d3ify(figureHandle, saveFileName, d3Params)
	Inputs (default):
	  -- figureHandle (gcf)
	  -- saveFileName ('d3ifyFigure'): a string
	  -- d3Params: a structure containing the following fields (with subfields)
		    margin (top, right, bottom, left)
			width
			height
	
	Outputs:
	  -- index.html 
	  -- saveFileName.js
	  -- saveFileNameData.csv


examples
--------
	% Ex 1
	x = 0:.01:2*pi;
	y = sin(x) + .25*randn(size(x));
	
	figure;
	plot(x, y, 'lineWidth', 2, 'color', [.25 .25 .75]);
	d3ify(gcf, 'mat2d3Test');

	% Ex 2
	

notes
-----
Make sure that D3.js is in the same folder as the output files of `d3ify`, otherwise, you won't see anything.

supported plot options
----------------------
The following name value pairs are transliterated by `d3ify`. When only a subset of a name's options are supported, the supported values are indicated by `Name -- 'val 1', 'val 2', etc`.
### plot ###
	LineStyle -- '-'
	LineWidth
	Color
	Marker -- '.'
	MarkerSize
### x(y) label ###
	String



