<template>
  
      <div class="card">
            
            <div class="img-wrap">
                <img :src="albumShow.poster">
            </div>
           
            
            <div class="album-name">
                <h3>{{albumShow.title}}</h3>
            </div>

            <div class="artist-year">
                <h4>{{albumShow.author}}</h4>
                <h5>{{albumShow.year}}</h5>
            </div>
        </div>
  
</template>

<script>
export default {
  name: 'cardAlbum',
  props: ['albumShow'],
}
</script>

<style lang="scss" scoped>

  @import "../../assets/style/main.scss";

</style>