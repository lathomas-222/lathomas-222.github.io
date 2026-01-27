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
<script>
  var locations = [
    {
      name: "Lower Mississippi River",
      coords: [34.8, -91.1],
      link: "/publication/mississippi-sediment/",
      label: "Sediment dynamics study (2022)"
    },
    {
      name: "Columbia River",
      coords: [46.2, -123.9],
      link: "/publication/columbia-carbon/",
      label: "Carbon burial rates (2023)"
    }
  ];

  locations.forEach(function(loc) {
    L.marker(loc.coords)
      .addTo(map)
      .bindPopup(
        `<strong>${loc.name}</strong><br>
         <a href="${loc.link}">${loc.label}</a>`
      );
  });
</script>
var bounds = L.latLngBounds(locations.map(l => l.coords));
map.fitBounds(bounds);


