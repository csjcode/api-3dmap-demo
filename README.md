# 3D Map Demo

### Setup

* Initial html page + Leaflet in the Head + initialization JS

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Building Gorgeous 3D maps with eegeo.js and Leaflet</title>
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.0.3/dist/leaflet.css" />
    <script src="https://unpkg.com/leaflet@1.0.3/dist/leaflet.js"></script>
  </head>
  <body>
    <div id="map" style="width: 600px; height: 400px;"></div>
    <script>
    var map = L.map('map', {
      center: [51.517327, -0.120005],
      zoom: 15
    });
    L.tileLayer('http://{s}.tile.osm.org/{z}/{x}/{y}.png', {
      attribution: '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors'
    }).addTo(map);
</script>
  </body>
</html>
```

* Map centered on Holborn Tube Station at the WGS84, decimal degrees latitude, longitude of 51.517327, -0.120005.

* Get coordinates by right clicking and selecting ‘What’s here’ on digital maps like maps.eegeo.com or Google Maps.

* eeGeo.js is built on top of Leaflet, so uses similar instructions

### 3D map with eeGeo

* change code to :

```javascript
var map = L.eeGeo.map('map', '<api key>', {
  center: [32.796325, -117.256731],
  zoom: 15
});
console.log('working');
```

* Now we have a 3d map (may only work on server due to cross-origin - not on local)


### 3D map change heading, tilt, zoom

* map.setView is type of scene
* [32.851105, -117.272999] is new location
* headingDegrees 0 is north, tiltDegrees:20.0 (0 is height/tilt)


```javascript

var map = L.eeGeo.map('map', '<api key>', {
  center: [32.796325, -117.256731],
  zoom: 15
});
console.log('working');

setTimeout(function() {
  map.setView([32.851105, -117.272999], 14, {headingDegrees: 150, tiltDegrees:20.0});
}, 20000);


```


### Adding pins

Adding a marker:  

`L.marker([32.850596, -117.273352]).addTo(map);`

Adding several markers:  

```javascript
var map = L.eeGeo.map('map', '<api key>', {
  center: [32.796325, -117.256731],
  zoom: 15
});
console.log('working');

setTimeout(function() {
  map.setView([32.851105, -117.272999], 14, {headingDegrees: 150, tiltDegrees:20.0});
}, 20000);

L.marker([32.850596, -117.256731]).addTo(map);
L.marker([32.850596, -117.273362]).addTo(map);
L.marker([32.850596, -117.273472]).addTo(map);
L.marker([32.850596, -117.273682]).addTo(map);
L.marker([32.850596, -117.273992]).addTo(map);

```




















######
