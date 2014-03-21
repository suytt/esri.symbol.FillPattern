esri.symbol.FillPattern
=======================

Display esri.symbol.SimpleFillSymbol fill patterns with the color defined instead of the default black pattern.

Just include the JS file and proceed as usual with the [simple fill symbol](https://developers.arcgis.com/javascript/jsapi/simplefillsymbol-amd.html)

`new SimpleFillSymbol(SimpleFillSymbol.STYLE_CROSS, null, new Color([255, 0, 0]))`

Browser compatibility : [data uri](http://caniuse.com/#feat=datauri)


Example
=======

```HTML
<!DOCTYPE html>
<html>
<head>
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
	<meta name="viewport" content="initial-scale=1, maximum-scale=1,user-scalable=no"/>
	<title>Simple Map</title>
	<link rel="stylesheet" href="http://js.arcgis.com/3.8/js/esri/css/esri.css">
	<style>
		html, body, #map { height: 100%; width: 100%; margin: 0; padding: 0; }
		body { background-color: #FFF; overflow: hidden; font-family: "Trebuchet MS"; }
	</style>
	<script src="http://js.arcgis.com/3.8/"></script>
	<script src="https://raw.githubusercontent.com/Chaussette/esri.symbol.FillPattern/master/esri.symbol.FillPattern.js"></script>
	<script>
	var map;
	require(["esri/map", "esri/symbols/SimpleFillSymbol", "dojo/_base/Color", "esri/graphic", "esri/geometry/Polygon", "dojo/domReady!"], 
	function(Map, SimpleFillSymbol, Color, Graphic, Polygon)
	{
		map = new Map("map", { basemap: "topo", center: [0,0], zoom: 4, sliderStyle: "small" });
		map.on("load", function()
		{
			map.graphics.add(new Graphic(
				new Polygon([[-50, 0], [50, 50], [50, -50], [-50,0]]), 
				new SimpleFillSymbol(SimpleFillSymbol.STYLE_CROSS, null, new Color([255, 0, 0])),
				{})
			);
		});
	  });
	</script>
</head>
<body>
	<div id="map"></div>
</body>
</html>
```
