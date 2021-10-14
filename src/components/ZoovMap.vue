<template>
    <div>
        <!-- {{bikes}} -->
        <l-map style="height: 300px" :zoom="zoom" :center="center">
        <l-tile-layer :url="url" :attribution="attribution"></l-tile-layer>
        <l-marker :lat-lng="markerLatLng"></l-marker>
    </l-map>
    </div>
</template>

<script>
import {LMap, LTileLayer, LMarker} from 'vue2-leaflet';



export default {
    name: "ZoovMap",
    props: {
        bikes: Array
    },
    data: function() {
        return {
            url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
            attribution:
                '&copy; <a target="_blank" href="http://osm.org/copyright">OpenStreetMap</a> contributors',
            zoom: 13,
            center: [51.505, -0.159],
            markerLatLng: [2.3522219, 48.856614]
        }
    },
    components: {
        LMap,
        LTileLayer,
        LMarker
    }
}
</script>

<style scoped>

</style>