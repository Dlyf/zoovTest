<template>
    <div id="mapContainer" class="basemap">
        <l-map style="height: 300px" :zoom="zoom" :center="center">
          <l-tile-layer :url="url" :attribution="attribution"></l-tile-layer>
          <l-marker :lat-lng="markerLatLng"></l-marker>
      </l-map>
        {{bikes}}
        <!-- <h2>map</h2> -->
    </div>
</template>

<script>
import {LMap, LTileLayer, LMarker} from 'vue2-leaflet';
// import mapboxgl   from 'mapbox-gl/dist/mapbox-gl.js';
// import 'mapbox-gl/dist/mapbox-gl.css';
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
      // accessToken: 'pk.eyJ1IjoiZGx5Zjc1IiwiYSI6ImNrdXF5aWt0dTA4ejIydm8yMGU2ZThoY3oifQ.K__SRuLxuUJSdrJPDdlu8w',
      url: 'https://api.mapbox.com/styles/v1/mapbox/streets-v10/tiles/256/{z}/{x}/{y}?title=view&access_token=pk.eyJ1IjoiZGx5Zjc1IiwiYSI6ImNrdXF5aWt0dTA4ejIydm8yMGU2ZThoY3oifQ.K__SRuLxuUJSdrJPDdlu8w&zoomwheel=true&fresh=true#9/37.78/-122.4241',
      attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
      zoom: 15,
      center: [51.505, -0.159],
      markerLatLng: [51.504, -0.159]
    };
  },
  // mounted() {
    // mapboxgl.accessToken = this.accessToken;

    // add map
    // const map = new mapboxgl.Map({
    //   container: "mapContainer",
      // style: "mapbox://styles/mapbox/streets-v11",
      // center: [-74.5, 40],
      // zoom: 10,
      // maxBounds: [
      //   [103.6, 1.1704753],
      //   [104.1, 1.4754753],
      // ],
    // });
    // add Marker
    // new mapboxgl.Marker()
    //   .setLngLat([2.30082, 48.7546])
    //   .addTo(map);

    // new mapboxgl.Marker()
    //   .setLngLat([2.30091, 48.765 ])
    //   .addTo(map);

    // new mapboxgl.Marker()
    //   .setLngLat([2.32145, 48.7566 ])
    //   .addTo(map);

    // new mapboxgl.Marker()
    //   .setLngLat([2.32013, 48.7543 ])
    //   .addTo(map);

    // new mapboxgl.Marker()
    //   .setLngLat([2.32025, 48.7647 ])
    //   .addTo(map);

    // new mapboxgl.Marker()
    //   .setLngLat([2.37085, 48.6566 ])
    //   .addTo(map);

    // new mapboxgl.Marker()
    //   .setLngLat([2.37087, 48.6546 ])
    //   .addTo(map);

    // new mapboxgl.Marker()
    //   .setLngLat([2.24344, 48.7711 ])
    //   .addTo(map);
    // Create a default Marker, colored black, rotated 45 degrees.
    // new mapboxgl.Marker({ color: 'black', rotation: 45 })
    //   .setLngLat([12.65147, 55.608166])
    //   .addTo(map);
    // },

  components: {
    LMap, LTileLayer, LMarker
  },
  methods: {

  }
}
</script>

<style scoped>

.basemap {
  /* margin-top: 300px; */
  /* height: 80vh; */
  height: 180px;

}


</style>