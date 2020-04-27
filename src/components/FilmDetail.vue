<template lang="html">
  <div class="">
    <ul>
      <li>Title: {{filmSelect.title}}</li>
      <li>Episode ID: {{filmSelect.episode_id}}</li>
      <li>Release Date: {{filmSelect.release_date}}</li>
      <li>Director: {{filmSelect.director}}</li>
    </ul>
    <div class="character-details">
      <ul>
        <character-list :characterList="characterList"></character-list>
      </ul>
    </div>
  </div>
</template>

<script>
import {eventBus} from "../main.js";
import CharacterList from "./CharacterList.vue"

export default {
  name: "film-detail",
  props: ["filmSelect"],
  components: {
    "character-list": CharacterList
  },
  data(){
    return{
      characterList: []
    }
  },
  methods: {
    getCharacterData(){
      const characterListPromises = this.filmSelect.characters.map((CharURL) => {
        return fetch(CharURL).then(res => res.json())
      })
      Promise.all(characterListPromises).then(data => this.characterList = data)
    }
  },
  mounted(){
    this.getCharacterData();
  },
  watch: {
    filmSelect: function(){ //We use the filmSelect prop. What is this method saying?
      this.getCharacterData();
    }
  }
}
</script>

<style lang="css" scoped>
</style>
