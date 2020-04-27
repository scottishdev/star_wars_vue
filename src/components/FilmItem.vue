<template lang="html">
  <div>
      <li v-on:click="handleOnClickSelect">{{filmItem.title}}</li>
  </div>
</template>

<script>
import {eventBus} from "../main.js"

export default {
  name: "film-item",
  props: ["filmItem"],
  methods: {
    handleOnClickSelect: function() {
      eventBus.$emit("film-select", this.filmItem)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
