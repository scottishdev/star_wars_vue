<template lang="html">
  <div class="">
    <li>Name: {{characterItem.name}}</li>
    <li>Gender: {{characterItem.gender}}</li>
    <li>Height: {{characterItem.height}}</li>
  </div>
</template>

<script>

export default {
  name: "character-item",
  props: ["characterItem"]
}
</script>

<style lang="css" scoped>
</style>
