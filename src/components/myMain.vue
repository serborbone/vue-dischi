<template> 
  <section id="main">
    <div class="card-container">

        <cardAlbum 
          v-for="(album, index) in albumFiltered" 
          :key="index" :albumShow="album" 
        >
        </cardAlbum>

    </div>

  </section>
</template>

<script>

const axios = require('axios');

import cardAlbum from "./partials/cardAlbum.vue";

export default {
  name: 'myMain',

  props: [ 'genreToSearch'],

  components: {
    cardAlbum,
  },

  data() {

    return {
      albumList: [],

      genreList: [],

    }
  },

  methods: {
  
    getAlbum() {

        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
          this.albumList = response.data.response;

          this.getGenere();

        })
        .catch(function (error) {
          console.log(error);
        })
        .then(function () {
        });
        
    },


    getGenere() {
      for (let i = 0; i < this.albumList.length; i++) {
            
          if(!this.genreList.includes(this.albumList[i].genre)) {

              this.genreList.push(this.albumList[i].genre);

          }

        }
           this.$emit("genresReady", this.genreList);
    },


  },

  mounted() {
    this.getAlbum();
  },

  computed: {

    albumFiltered() {

      if (this.genreToSearch == "") {
      
        return this.albumList;
      
      } else {

        return this.albumList.filter(item => {

          return item.genre.includes(this.genreToSearch);
      
        });

      }
      
    }

  },    

}
</script>

<style lang="scss" scoped>

  @import "../assets/style/main.scss";

</style>