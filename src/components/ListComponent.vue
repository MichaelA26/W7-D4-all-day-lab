<template lang="html">
  <div>
    <li
    v-bind:class="{'favourited' : beer.favourited, 'notFavourited': !beer.favourited}"
    v-on:click="handleClick">{{beer.name}}
  </li>
  <button v-on:click="handleFavouriteClick">Add/Remove from Favourites</button>
</div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'list-component',
  props: ['beer'],
  methods: {
    handleClick(){
      eventBus.$emit('beer-selected', this.beer)
    },
    handleFavouriteClick(){
      eventBus.$emit('beer-favourited', this.beer)
    }
  }
}
</script>

<style lang="css" scoped>

.favourited {
  color: green;
}

.notFavourited {
  color: red;
}

</style>
