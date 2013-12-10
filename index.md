---
layout: default
title:  OSGeo Vienna Code Sprint 2014
---

<div class="jumbotron frontpage" style="position: relative;">
    <div id="map"></div>
    <div class="container">
        <h1>OSGeo &raquo; Code Sprint 2014</h1>
        <p>Get together, hack, decide, tackle large geospatial problems, have fun, and explore a city.<br />
            March 24th to 28th. Vienna, Austria.</p>
        <p style="margin-top: 1em"><a class="btn btn-primary btn-lg" href="{{ site.baseurl}}/sponsoring.html" style="text-shadow: none;">Sponsorhip Opportunities &raquo;</a></p>
    </div>
    <div id="terrain_attribution">
        <p style="float: right"><a href="#" onclick="toggle(terrain_attribution)">&#215;</a></p>
        <p>Terrain map data</p>
        <ul>
            <li>GTOPO30</li>
            <li>SRTM &copy; <a href='http://nasa.gov'>NASA</a></li>
            <li>EUDEM &copy; Produced using Copernicus data and information<br/>funded by the European Union - EU-DEM layers</li>
            <li>CleanTOPO2 public domain</li>
            <li>GlobCover &copy; <a href='http://esa.int'>ESA</a></li>
            <li>NaturalEarth <a href='http://www.naturalearthdata.com/about/terms-of-use/'>public domain</a></li>
            <li>OpenStreetMap &copy; <a href='http://www.openstreetmap.org'>OpenStreetMap contributors</a></li>
        </ul>
        <p>Terrain map design &copy; <a href='http://eox.at'>EOX IT Services GmbH</a></p>
    </div>
</div>

<div class="container">
        <h3>Gold Sponsors</h3>
        <ul class="sponsors">
            <li><a href="http://airborne.aero/" title="Airborne Interactive Ltd"><img src="{{ site.baseurl}}/assets/Logo-Airborne-Interactive.png" alt="Airborne Interactive Ltd" title="Airborne Interactive Ltd"/></a></li>
        </ul>

        <h3>Silver Sponsors</h3>
        <ul class="sponsors">
            <li>TBA</li>
        </ul>

        <h3>Bronze Sponsors</h3>
        <ul class="sponsors">
            <li><a href="http://www.metaspatial.net/en/institute" title="metaspatial Institute"><img src="{{ site.baseurl}}/assets/Logo-metaspatial.png" alt="metaspatial Institute" title="metaspatial Institute"/></a></li>
        </ul>

        <h3>Venue Sponsor</h3>
        <ul class="sponsors">
            <li><a href="http://www.wien.gv.at/english/administration/ict/index.html" title="City of Vienna MA 14"><img src="{{ site.baseurl}}/assets/Logo-City-of-Vienna.png" alt="City of Vienna MA 14" title="City of Vienna MA 14"/></a></li>
        </ul>

        <h3>Other/in-kind sponsor</h3>
        <ul class="sponsors">
            <li><a href="http://eox.at"><img src="{{ site.baseurl}}/assets/Logo-EOX.png" alt="EOX IT Services GmbH" title="EOX IT Services GmbH"></a></li>
        </ul>
</div>

<script src="//maps.eox.at/lib/openlayers/OpenLayers.js"></script>
<script type="text/javascript">
function toggle(e) { e.style.display = (e.style.display == 'block' ? 'none' : 'block'); }

// Some defaults for various map layers
layerDefaults = {
    requestEncoding: 'REST',
    attribution: '&copy; EOX IT Services GmbH',
    url: [ 'http://a.tiles.maps.eox.at/wmts/','http://b.tiles.maps.eox.at/wmts/','http://c.tiles.maps.eox.at/wmts/','http://d.tiles.maps.eox.at/wmts/','http://e.tiles.maps.eox.at/wmts/' ],
    matrixSet: 'WGS84',
    style: 'default',
    format: 'image/png',
    resolutions: [ 0.70312500000000000000,0.35156250000000000000,0.17578125000000000000,0.08789062500000000000,0.04394531250000000000,0.02197265625000000000,0.01098632812500000000,0.00549316406250000000,0.00274658203125000000,0.00137329101562500000,0.00068664550781250000,0.00034332275390625000,0.00017166137695312500 ],
    maxExtent: new OpenLayers.Bounds(-180,-90,180,90),
    displayOutsideMaxExtent: false,
    projection: new OpenLayers.Projection('EPSG:4326'),
    gutter: 0,
    buffer: 0,
    units: 'dd',
    transitionEffect: 'resize',
    isphericalMercator: false,
    isBaseLayer: false,
    wrapDateLine: true,
    zoomOffset: 0
};

var terrain = new OpenLayers.Layer.WMTS(OpenLayers.Util.applyDefaults({ name: 'Terrain', layer: 'terrain', isBaseLayer: true, attribution: "Terrain &copy; <a href='#' onClick='toggle(terrain_attribution)'>Various</a>" }, layerDefaults));
var map = new OpenLayers.Map({ div: 'map', projection: 'EPSG:4326', displayProjection: 'EPSG:4326' });
map.addLayers([ terrain ]);
map.setCenter(new OpenLayers.LonLat(16.3731,48.2083), 10);
</script>
