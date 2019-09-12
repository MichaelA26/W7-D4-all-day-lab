<template lang="html">
<p>helloooooo</p>
</template>

<script>
import ListComponent from './ListComponent.vue';

export default {
  name: 'beers-list',
  props: ['beers'],
  components: {
    "list-component": ListComponent
  }
}
</script>

<style lang="css" scoped>
</style>
