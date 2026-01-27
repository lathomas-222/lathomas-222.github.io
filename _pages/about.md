---
permalink: /
title: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
I'm a graduate student at the University of Colorado Boulder studying how human alteration has impacted floodplain carbon storage. Check out some of the research I've contributed to:

<div id="map" style="height: 400px; margin: 2em 0;"></div>
<link
  rel="stylesheet"
  href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"
/>

<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
<script>
  var map = L.map('map').setView([39.5, -98.35], 4);

  L.tileLayer(
    'https://{s}.basemaps.cartocdn.com/light_all/{z}/{x}/{y}{r}.png',
    {
      attribution: '&copy; OpenStreetMap &copy; CARTO',
      subdomains: 'abcd',
      maxZoom: 20
    }
  ).addTo(map);
</script>

<script>
  var locations = [
    {
      name: "Teller Road mm 27",
      coords: [64.7458, -165.9642],
      link: "/publication/2025-04-16-snow_shrub",
      label: "Shrub-Snow Interactions (2025)"
    },
    {
      name: "Rum River Floodplain",
      coords: [45.599968, -93.264123],
      link: "/publication",
      label: "Current Research"
    },
    {
      name: "San Pedro River Floodplain",
      coords: [32.791884, -110.683569],
      link: "/publication",
      label: "Current Research"
    },
    {
      name: "Kougarok Fire Complex",
      coords: [65.463953, -164.684980],
      link: "/publication/2024-01-01-rainfall-simulator",
      label: "Rainfall Simulator (2024)"
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
  var bounds = L.latLngBounds(locations.map(l => l.coords));
map.fitBounds(bounds);
</script>



