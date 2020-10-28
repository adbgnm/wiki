
### Initialiseren
```
      <link rel="stylesheet" href="https://unpkg.com/leaflet@1.0.0-rc.3/dist/leaflet.css">
      <!-- Make sure you put this AFTER Leaflet's CSS -->
      <script src="https://unpkg.com/leaflet@1.0.0-rc.3/dist/leaflet.js"></script>
```
### Proj4 and Proj4Leaflet
````  <script src="https://unpkg.com/proj4@2.4.3/dist/proj4-src.js"></script>
      <script src="https://unpkg.com/proj4leaflet@1.0.1"></script>
````

### map_init in RD

HTML:
``` 
<div id="map"></div>
```

CSS:
```
#map {
	// Specific size
        height: 460px;
	width: 920px;

       // Full screen
       height: auto;
       width: 100%;
	
}
```
Javascript:
``` 
var map_init = function() {
				
	var RD = new L.Proj.CRS(
		'EPSG:28992',
		'+proj=sterea +lat_0=52.15616055555555 +lon_0=5.38763888888889 +k=0.9999079 +x_0=155000 +y_0=463000 +ellps=bessel +units=m +towgs84=565.2369,50.0087,465.658,-0.406857330322398,0.350732676542563,-1.8703473836068,4.0812 +no_defs', {
		origin: [-285401.92, 22598.08],
		resolutions: [3440.640, 1720.320, 860.160, 430.080, 215.040, 107.520, 53.760, 26.880, 13.440, 6.720, 3.360, 1.680, 0.840, 0.420, 0.210, 0.105],
		bounds: L.bounds([-285401.92, 22598.08], [595401.920, 903401.920])
	});

map = new L.map('map', {minZoom: 3, maxZoom: 14, zoomControl: false, drawControl:true, crs: RD).setView([52.155185136850555, 5.387434343246395], 13);
```

## Basiskaarten PDOK

```
	tms_brt = L.tileLayer('https://geodata.nationaalgeoregister.nl/tiles/service/tms/1.0.0/brtachtergrondkaart/EPSG:28992/{z}/{x}/{y}.png', {
		attribution: 'Basisregistratie Topografie | PDOK', tms: true, opacity: 1
	});
	
	tms_bgt = L.tileLayer('https://geodata.nationaalgeoregister.nl/tiles/service/tms/1.0.0/bgtachtergrond/EPSG:28992/{z}/{x}/{y}.png', {
		attribution: 'Basisregistratie Grootschalige Topografie | PDOK', tms: true,  opacity: 1
	});

	tms_luchtfoto = L.tileLayer('https://geodata.nationaalgeoregister.nl/luchtfoto/rgb/tms/1.0.0/2018_ortho25/EPSG:28992/{z}/{x}/{y}.png',{
		tms: true, opacity: 0
	});	
	
	tms_hoogtekaart = L.tileLayer('https://geodata.nationaalgeoregister.nl/tiles/service/tms/1.0.0/ahn1_5m/EPSG:28992/{z}/{x}/{y}.png',{
		tms: true, opacity: 0
	});	
	
	tms_kadastralekaart = L.tileLayer('https://geodata.nationaalgeoregister.nl/tiles/service/tms/1.0.0/kadastralekaartv3/EPSG:28992/{z}/{x}/{y}.png',{
		tms: true, opacity: 0
	});	
	
		
	map = new L.map('map', {minZoom: 3, maxZoom: 14, zoomControl: false, drawControl:true, crs: RD, layers: [tms_hoogtekaart, tms_luchtfoto,tms_brt, tms_bgt, tms_kadastralekaart]}).setView([52.155185136850555, 5.387434343246395], 13);
```

### GeoJSON layer

```
var geojson_layer =L.geoJson();

```
