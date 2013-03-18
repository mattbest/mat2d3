mat2d3 -- a Matlab toolkit for generating d3.js visualizations
==============================================================
[D3.js](http://d3js.org/ "D3") is an excellent javascript library for creating visualizations.  This toolkit creates skeleton code for a D3 figure from a matlab figure handle.

syntax
------
	d3ify(figureHandle, saveFileName)
	Inputs (default):
	  -- figureHandle (gcf)
	  -- saveFileName ('d3ifyFigure')
	
	Outputs:
	  -- index.html 
	  -- saveFileName.js
	  -- saveFileNameData.csv


examples
--------
	x = 0:.01:2*pi;
	y = sin(x) + .25*randn(size(x));

	plot(x, y, 'lineWidth', 2, 'color', [.25 .25 .75]);
	d3ify(gcf, 'mat2d3Test');

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



