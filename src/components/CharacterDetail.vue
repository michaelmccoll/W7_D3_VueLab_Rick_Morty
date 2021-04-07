<template>
  <section>
      <h3>{{character.name}}</h3>
      <p>Species: {{character.species}}</p>
      <p v-if="character.type">Type: {{character.type}}</p>
      <p>Gender: {{character.gender}}</p>
      <p>Status: {{character.status}}</p>
      <p>Origin: {{character.origin.name}}</p>
      <img class="image" :src="character.image" alt="">
  </section>
</template>

<script>
export default {
    name: 'character-detail',
    props: ['character']
}
</script>

<style>
.image {
    height: 250px;
    width: 250px;
}

</style>