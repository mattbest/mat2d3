mat2d3 - a Matlab toolkit for generating d3.js visualizations
==============================================================

mat2d3 aims to make it as simple as possible to translate a 2D Matlab figure into a d3.js visualization.

Here's a few examples.  In order for them to run properly, mat2d3 must be in your current path.  Each example will create 3 files, mat2d3TestData.csv, which contains the plot data, mat2d3Test.js, which contains the d3.js code, and index.html, which contains style information.  To view your plot, simply view index.html in your favorite browser.

examples
--------
	% Ex 1
	x = 0:.01:2*pi;
	y = sin(x) + .25*randn(size(x));
	
	figure;
	plot(x, y, '.', 'markerSize', 8, 'color', [.25 .25 .75]);
	d3ify(gcf, 'mat2d3Test');

	% Ex 2
	y = [sin(x); sin(x + pi/16); sin(x + pi/8); ...
		sin(x + 3*pi/16); sin(x + pi/4)];
	figure;
	set(gca, 'nextPlot', 'replaceChildren');
	set(gca, 'colorOrder', jet(5))
	plot(x, y, 'lineWidth', 2)
	d3ify(gcf, 'mat2d3Test')

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
			plotType ('cart'): a string indicating whether the axes should be in cartesian or polar coordinates.  
	
	Outputs:
	  -- index.html 
	  -- saveFileName.js
	  -- saveFileNameData.csv

supported plot options
----------------------
The following name value pairs are transliterated by `d3ify`. When only a subset of a name's options are supported, the supported values are indicated by `Name -- 'val 1', 'val 2', etc`.
### plot ###
	LineStyle -- '-'
	LineWidth
	Color
	Marker -- '.'
	MarkerSize
### polar plots (rose, polar) ###
	LineStyle -- '-'
	LineWidth
	Color
### x(y) label ###
	String



