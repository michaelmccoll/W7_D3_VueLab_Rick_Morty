<template>
  <li @click="handleClick">{{character.name}}</li>
</template>

<script>
import {eventBus} from '../main.js'

export default {
    name: 'list-item',
    props: ['character'],
    methods: {
        handleClick: function(){
            eventBus.$emit('character-selected', this.character);
        }
    }

}
</script>

<style>

</style>