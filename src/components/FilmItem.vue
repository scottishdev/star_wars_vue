<template lang="html">
  <div>
      <li>{{filmItem.title}}</li>
  </div>
</template>

<script>
import {eventBus} from "../main.js"

export default {
  name: "film-item",
  props: ["filmItem"]
}
</script>

<style lang="css" scoped>
</style>
