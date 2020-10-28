## Initialiseren
```
<script src='https://api.mapbox.com/mapbox-gl-js/v1.6.1/mapbox-gl.js'></script>
<link href='https://api.mapbox.com/mapbox-gl-js/v1.6.1/mapbox-gl.css' rel='stylesheet' />
```

## Vector tiles layer


```

map.addLayer(
   {
   'id': 'extrusion',
   'type': 'fill-extrusion',
   'source': {
   'type': 'vector',
   'tiles': [
   'terrein.z1.mbtiles'
   ],
   'minzoom': 6,
   'maxzoom': 14
   },
   'source-layer': 'mapillary-sequences',
   //'layout': {
   //'line-cap': 'round',
   //'line-join': 'round'
   //},
   'paint': {	
      fill-extrusion-color': '#aaa',
      / use an 'interpolate' expression to add a smooth transition effect to the
      / buildings as the user zooms in
      /'fill-extrusion-height': ['interpolate', ['linear'],['zoom'],['get', 'exh']],
      fill-extrusion-height': ['interpolate',
      							['linear'],['get', 'exh'], 0, 10,
                                        100,20,
                                        200, 30,
                                        300, 40],
      fill-extrusion-height': ['get', 'exh'],
      fill-extrusion-base': 0,
      fill-extrusion-opacity': 1,
      'fill-extrusion-color': [
      'interpolate',
      ['linear'],
      ['get', 'exh'],
       0, '#F2F12D',
       100, '#EED322',
       200, '#E6B71E',
      300, '#DA9C20',
      ]					
   	}
   },
   //'terrein-label'
   );
   });
