<template> 
  <section id="main">
  
    <div class="card-container">

        <cardAlbum v-for="(album, index) in albumList" :key="index" :albumShow="album">
        </cardAlbum>

    </div>

  </section>
</template>

<script>

const axios = require('axios');

import cardAlbum from "./cardAlbum.vue";

export default {
  name: 'myMain',

  components: {
    cardAlbum,
  },

  data() {

    return {
      albumList: [],
    }
  },

  methods: {
  
    getAlbum() {

        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
          // handle success
          this.albumList = response.data.response;
          //console.log(response);
        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
        .then(function () {
          // always executed
        });
    },
  },

  mounted() {
    this.getAlbum();
  }    

}
</script>

<style lang="scss" scoped>

  @import "../assets/style/main.scss";

</style>