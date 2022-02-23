<template>
  <div id="app">

    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <myHeader></myHeader>
    <myMain></myMain>
    <cardAlbum></cardAlbum>

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import myHeader from './components/myHeader.vue'
import myMain from './components/myMain.vue'
import cardAlbum from './components/cardAlbum.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    myHeader,
    myMain,
    cardAlbum,
  }
}
</script>

<style lang="scss">

  @import "./assets/style/general.scss";

</style>
