# Map Layers

## Basemaps

### PDOK

```
tms_brt = L.tileLayer('https://geodata.nationaalgeoregister.nl/tiles/service/tms/1.0.0/brtachtergrondkaart/EPSG:28992/{z}/{x}/{y}.png', {
					  attribution: 'Basisregistratie Topografie | PDOK', tms: true, opacity: 1
					 });
	
tms_bgt = L.tileLayer('https://geodata.nationaalgeoregister.nl/tiles/service/tms/1.0.0/bgtachtergrond/EPSG:28992/{z}/{x}/{y}.png', {
					  attribution: 'Basisregistratie Grootschalige Topografie | PDOK', tms: true,  opacity: 1
					  });

tms_luchtfoto = L.tileLayer('https://geodata.nationaalgeoregister.nl/luchtfoto/rgb/tms/1.0.0/2018_ortho25/EPSG:28992/{z}/{x}/{y}.png',{
							 attribution: 'Beeldmateriaal | PDOK', 
							 tms: true, 
							 opacity: 0
    						});	
	
tms_hoogtekaart = L.tileLayer('https://geodata.nationaalgeoregister.nl/tiles/service/tms/1.0.0/ahn1_5m/EPSG:28992/{z}/{x}/{y}.png',{
							  attribution: 'Actueel Hoogtebestand Nederland | PDOK', 
							  tms: true, 
							  opacity: 0
						     });	
	
tms_kadastralekaart = L.tileLayer('https://geodata.nationaalgeoregister.nl/tiles/service/tms/1.0.0/kadastralekaartv3/EPSG:28992/{z}/{x}/{y}.png',{
								  attribution: 'Kadastrale Kaart | PDOK', 
								  tms: true, 
								  opacity: 0
								 });	
```
