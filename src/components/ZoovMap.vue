<template>
    <div id="mapContainer" class="basemap">
        <!-- {{bikes}} -->
        <!-- <l-map style="height: 300px" :zoom="zoom" :center="center">
        <l-tile-layer :url="url" :attribution="attribution"></l-tile-layer>
        <l-marker :lat-lng="markerLatLng"></l-marker>
        </l-map> -->
        <!-- <mapbox
            access-token="pk.eyJ1IjoiZGx5Zjc1IiwiYSI6ImNrdXF5aWt0dTA4ejIydm8yMGU2ZThoY3oifQ.K__SRuLxuUJSdrJPDdlu8w"
            :map-options="{
                container: 'map',
                style: 'mapbox://styles/mapbox/light-v9',
                center: [-96, 37.8],
                zoom: 3,
            }"
        /> -->
        <!-- <mapboxgl /> -->
        <h2>Map</h2>

           <!-- <MglMap :accessToken="accessToken" :mapStyle="mapStyle" /> -->

        <!-- <mapboxgl /> -->
    </div>
</template>

<script>
// import {LMap, LTileLayer, LMarker} from 'vue2-leaflet';
import mapboxgl   from 'mapbox-gl/dist/mapbox-gl.js';
// bug with this package ?
// import Mapbox from "mapbox-gl";
// import { MglMap } from "vue-mapbox";

export default {
    name: "ZoovMap",
    props: {
        bikes: Array
    },
    data() {
    return {
      accessToken: 'pk.eyJ1IjoiZGx5Zjc1IiwiYSI6ImNrdXF5aWt0dTA4ejIydm8yMGU2ZThoY3oifQ.K__SRuLxuUJSdrJPDdlu8w',
    };
  },
  mounted() {
    mapboxgl.accessToken = this.accessToken;

    new mapboxgl.Map({
      container: "mapContainer",
      style: "mapbox://styles/mapbox/streets-v11",
      center: [103.811279, 1.345399],
      zoom: 12,
      maxBounds: [
        [103.6, 1.1704753],
        [104.1, 1.4754753],
      ],
    });
  },
}
</script>

<style scoped>
/* #map {
  width: 100%;
  height: 500px;
} */
.basemap {
  width: 100%;
  height: 100%;
}
</style>