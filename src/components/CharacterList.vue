<template lang="html">
  <div class="">
    <ul>
      <h4>Character List</h4>
      <character-item v-for="(characterItem, index) in characterList" :characterItem="characterItem" :key="index"></character-item>
    </ul>
  </div>
</template>

<script>
import CharacterItem from "./CharacterItem.vue"

export default {
  name: "character-list",
  props: ["characterList"],
  components: {
    "character-item": CharacterItem
  }
}
</script>

<style lang="css" scoped>
</style>
