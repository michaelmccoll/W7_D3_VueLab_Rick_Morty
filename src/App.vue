<template>
  <div id="app">
    <h1>Rick & Morty Characters</h1>
    <characters-list :characters='characters'></characters-list>
    <character-detail v-if="selectedCharacter" :character="selectedCharacter"></character-detail>    
  </div>
</template>

<script>
import CharacterDetail from './components/CharacterDetail.vue';
import CharacterList from './components/CharacterList.vue';
import {eventBus} from './main.js'


export default {
  name: 'App',
  data(){
    return {
      characters: [],
      selectedCharacter: null
    };
  },
  mounted () {
    fetch('https://rickandmortyapi.com/api/character/')
    .then(res => res.json())
    .then(characters => this.characters = characters.results)

    eventBus.$on('character-selected',(character)=>{
      this.selectedCharacter = character;
    })
  },
  components: {
    "characters-list": CharacterList,
    "character-detail": CharacterDetail,    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
