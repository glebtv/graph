Graph
=====

There are many good Javascript/HTML5 graphing libraries already in existence e.g. [Flot](https://github.com/flot/flot) or [D3](http://mbostock.github.com/d3/). However, they don't make the simple xy data graphs often used in scientific environments. I decided to write my own graphing library that could deal with large amounts of data as well as logarithmic axes and page resizing. This was created as part of my work at Las Cumbres Observatory Global Telescope (LCOGT).

Dependencies
------------

For this library to work it has two dependencies:

* [jquery.js](http://jquery.com/) -- your site may already use this excellent library;
* [excanvas.js](http://code.google.com/p/explorercanvas/) -- this is used to allow canvas support on Internet Explorer (41.6 kB). If only it wasn't needed.


Limitations
-----------
Some features (e.g. fullscreen) are experimental and will only work in the latest versions of modern browsers.

Usage
-----
You need to include the appropriate Javascript files:

	<script src="jquery.js"></script>
	<script src="excanvas.js"></script>
	<script src="jquery.graph.js"></script>

Following those you'll need:
	$(document).ready(function(){
		var dataset = [];
		dataset.push({data: [[0,0.1],[1,0.2],[2,0.1],[3,0.25]], color: '#FFBBDD', points: {show:true}, lines: {show:true,lineWidth:2}, clickable: false, hoverable:false});
		options = {
			xaxis:{ label:'Time (HJD)' },
			yaxis: { label: 'Delta (mag)' },
			grid: { hoverable: true, clickable: true }
		};
		// Attach to the DOM element with the ID 'lightcurve'
		graph = $.graph('lightcurve', dataset, options);
	});


Author
------
Stuart Lowe works for the [Las Cumbres Observatory Global Telescope](http://lcogt.net/). LCOGT is a private operating foundation, building a global network of telescopes for professional research and citizen investigations.

