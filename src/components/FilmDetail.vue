<template lang="html">
  <div class="">
    <ul>
      <li>Title: {{filmSelect.title}}</li>
      <li>Episode ID: {{filmSelect.episode_id}}</li>
      <li>Release Date: {{filmSelect.release_date}}</li>      
      <li>Director: {{filmSelect.director}}</li>
    </ul>
  </div>
</template>

<script>
import {eventBus} from "../main.js";

export default {
  name: "film-detail",
  props: ["filmSelect"]
}
</script>

<style lang="css" scoped>
</style>
