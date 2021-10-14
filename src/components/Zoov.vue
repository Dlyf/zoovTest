<template>
  <div class="hello">
    <h1>Bike List Map</h1>
      <ul>
        <!-- recuperate and display data -->
        <li v-for="item in bikes" :key="item.id">
          {{item.id}}, {{item.serial_number}}
        </li>
      </ul>
        <div>
          {{bikes}}
        </div>
  </div>

</template>

<script>
import axios from 'axios';
import ZoovMap from './ZoovMap.vue';

export default {

  name: 'Bikes',
  component: {ZoovMap},
  data() {
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
      this.bikes = res.data.bikes
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
