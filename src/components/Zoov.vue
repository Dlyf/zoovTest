<template>
  <div class="hello">
    <h1>Bike List Map</h1>
      <ul>
        <!-- recuperate and display data -->
        <li v-for="(bike, item) in bikes" :key="item.id">
         {{item}}, {{bike.serial_number}}, {{bike.location.coordinates}}, {{bike.service_status}}
        </li>
      </ul>
        <!-- display all data -->
          <ZoovMap :bikes="bikes" />
          <!-- <zoov-map/> -->

  </div>

</template>

<script>
import axios from 'axios';
import ZoovMap from './ZoovMap.vue';

export default {
  name: 'Bikes',
  components: { ZoovMap },
  data: function () {
    return {
      bikes: []
    };
  },

  async mounted() {
    try {
       const res = await axios.get('https://615d9d1612571a001720773d.mockapi.io/bikes')
    // axios.get('https://api.openbrewerydb.org/breweries')
      // .then((r) => {
      //   // this.bikes = r.data;
        console.log("test", res.data.bikes)
      //   this.bikes = r.data
      // })
      this.bikes = res.data.bikes.filter(res => res)
    } catch (e) {
      console.error(e);
    }
  }
}

</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
