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

* 
