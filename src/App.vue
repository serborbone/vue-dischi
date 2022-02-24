<template>
  <div id="app">

    <myHeader :albumGenre="getGensAlbum" @changedGenre="startSearch"></myHeader>
    <myMain :genreToSearch="currentValue" @genresReady="pushGen"></myMain>
    <cardAlbum></cardAlbum>

  </div>
</template>

<script>
import myHeader from './components/myHeader.vue'
import myMain from './components/myMain.vue'
import cardAlbum from './components/partials/cardAlbum.vue'

export default {
  name: 'App',
  components: {
    myHeader,
    myMain,
    cardAlbum,
  },

  data() {
    return {
        getGensAlbum: [],

        currentValue: '',
    }
  },

  methods: {

    pushGen(genreReceived) {
    
        this.getGensAlbum = genreReceived;

        console.log(this.getGensAlbum);
    
    },

    startSearch(valueReceived) {
        this.currentValue = valueReceived;

        console.log(this.currentValue);
    }

  },
}
</script>

<style lang="scss">

  @import "./assets/style/general.scss";

</style>
