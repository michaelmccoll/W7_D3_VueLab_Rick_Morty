<template>
  <section>
      <h3>{{character.name}}</h3>
      <p>{{character.species}}</p>
      <p>{{character.type}}</p>
      <p>{{character.gender}}</p>
  </section>
</template>

<script>
export default {
    name: 'character-detail',
    props: ['character']
}
</script>

<style>

</style>