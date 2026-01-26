---
permalink: /
title: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
I am a graduate student in the Geography Department at the University of Colorado Boulder

<div id="map" style="height: 400px; margin: 2em 0;"></div>
<link
  rel="stylesheet"
  href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"
/>

<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
<script>
  var map = L.map('map').setView([39.5, -98.35], 4); // center US

  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; OpenStreetMap contributors'
  }).addTo(map);
</script>
<script>
  var site1 = L.marker([45.0, -93.0]).addTo(map);
  site1.bindPopup(`
    <strong>Minnesota Floodplain</strong><br>
    <a href="/publication/2025-04-16-snow_shrubs" target="_blank">
      Floodplain carbon storage (2024)
    </a>
  `);
</script>
