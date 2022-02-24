<template>
  <section id="header">

    <div class="header">

        <!-- LOGO -->
        <a href="#">
          <img src="../assets/img/logo.png" alt="logo Spotify">
        </a>

        <div class="select">
          <label for="selectGenre">Filtra per genere: </label>
          <select id="selectGenre" v-model="selectValue" @change="getValueSelect">
            <option 
              v-for="(genre, index) in albumGenre" 
              :value="genre" 
              :key="index"
            >
                {{ genre }}
            </option>

          </select>
        </div>

    </div>

  </section>
</template>

<script>
export default {

  name: 'myHeader',
  props: ['albumGenre'],

  data() {
    return {
      selectValue: '',
    }
  },

  methods: {

    getValueSelect() {
    
      this.$emit('changedGenre', this.selectValue);
    
    } 

  },

}
</script>

<style lang="scss" scoped>

  @import "../assets/style/header.scss";
  
</style>