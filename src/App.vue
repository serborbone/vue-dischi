<template>
  <div id="app">

    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <myHeader></myHeader>
    <myMain></myMain>

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import myHeader from './components/myHeader.vue'
import myMain from './components/myMain.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    myHeader,
    myMain,
  }
}
</script>

<style lang="scss">

  @import "./assets/style/general.scss";

</style>
