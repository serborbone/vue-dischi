<template>
  <section id="header">

    <div class="header">

        <!-- LOGO -->
        <a href="#">
          <img src="../assets/img/logo.png" alt="logo Spotify">
        </a>

        <div class="select">
          <label for="selectGenre">Filtra per genere: </label>
          <select id="selectGenre">

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

}
</script>

<style lang="scss" scoped>

  @import "../assets/style/header.scss";
  
</style>