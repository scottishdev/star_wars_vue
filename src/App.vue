<template lang="html">
  <div>
    <star-wars-header></star-wars-header>
    <film-list :filmList="filmList"></film-list>
  </div>
</template>

<script>
import StarWarsHeader from "./components/Header.vue"
import FilmList from "./components/FilmList.vue"

export default {
  name: 'app',
  data(){
    return{
      filmList: []
    }
  },
  mounted() {
    fetch("https://swapi.dev/api/films/")
    .then(res => res.json())
    .then(filmList => this.filmList = filmList.results);
  },
  components: {
    "star-wars-header": StarWarsHeader,
    "film-list": FilmList
  }
}
</script>

<style lang="css" scoped>
</style>
