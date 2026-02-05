---
permalink: /
title: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
I'm a graduate student at the University of Colorado Boulder studying how human alteration has impacted floodplain carbon storage. Check out my research:

<div id="map" style="height: 400px; margin: 2em 0;"></div>
<link
  rel="stylesheet"
  href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"
/>

<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
<script>
  var map = L.map('map').setView([39.5, -98.35], 4);

  L.tileLayer(
    'https://server.arcgisonline.com/ArcGIS/rest/services/World_Topo_Map/MapServer/tile/{z}/{y}/{x}',
    {
      attribution: 'Tiles &copy; Esri'
    }
  ).addTo(map);
</script>

<script>
  var locations = [
    {
      name: "Teller Road mm 27",
      coords: [64.7458, -165.9642],
      link: "/publication/2025-04-16-snow_shrub",
      label: "Shrub-Snow Interactions (2025)",
      image: "/images/project1-photo.jpg"
    },
    {
      name: "Rum River Floodplain",
      coords: [45.599968, -93.264123],
      link: "/publication",
      label: "Current Research",
      image: "/images/project1-photo.jpg"
    },
    {
      name: "San Pedro River Floodplain",
      coords: [32.791884, -110.683569],
      link: "/publication",
      label: "Current Research",
      image: "/images/project1-photo.jpg"
    },
    {
      name: "Kougarok Fire Complex",
      coords: [65.463953, -164.684980],
      link: "/publication/2024-01-01-rainfall-simulator",
      label: "Rainfall Simulator (2024)",
      image: "/images/project1-photo.jpg"
    }
  ];

  locations.forEach(function(loc) {
  var popupContent = `<strong>${loc.name}</strong><br>`;
  
  if (loc.image) {
    popupContent += `<img src="${loc.image}" alt="${loc.label}" style="width:200px;height:auto;margin:5px 0;"><br>`;
  }
  
  popupContent += `<a href="${loc.link}">${loc.label}</a>`;
  
  L.marker(loc.coords)
    .addTo(map)
    .bindPopup(popupContent);
});
  
  var bounds = L.latLngBounds(locations.map(l => l.coords));
map.fitBounds(bounds);
</script>



