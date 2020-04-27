<template lang="html">
  <div class="">
  <ul>
    <film-item v-for="(filmItem, index) of filmList" :filmItem="filmItem" :key="index">
    </film-item>
  </ul>
    </div>
</template>

<script>
import FilmItem from "./FilmItem.vue"

export default {
  name: "film-list",
  props: ["filmList"],
  components: {
    "film-item": FilmItem
  }
}
</script>

<style lang="css" scoped>
</style>
