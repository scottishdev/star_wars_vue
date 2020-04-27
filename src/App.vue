<template lang="html">
  <div>
    <star-wars-header></star-wars-header>
    <film-list :filmList="filmList"></film-list>
    <film-detail v-if="filmSelect" :filmSelect="filmSelect"></film-detail>
  </div>
</template>

<script>
import {eventBus} from "./main.js"

import StarWarsHeader from "./components/Header.vue"
import FilmList from "./components/FilmList.vue"
import FilmDetail from "./components/FilmDetail.vue"

export default {
  name: 'app',
  data(){
    return{
      filmList: [],
      filmSelect: null
    }
  },
  mounted() {
    fetch("https://swapi.dev/api/films/")
    .then(res => res.json())
    .then(filmList => this.filmList = filmList.results);

    eventBus.$on("film-select",(film) => {this.filmSelect = film});
  },
  components: {
    "star-wars-header": StarWarsHeader,
    "film-list": FilmList,
    "film-detail": FilmDetail
  }
}
</script>

<style lang="css" scoped>
</style>
