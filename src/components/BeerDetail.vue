<template lang="html">
  <article v-if="beer">
    <p>Name: {{ beer.name }}</p>
    <p>Tagline: {{ beer.tagline }}</p>
    <p>A wee description: {{ beer.description }}</p>
    <p>ABV: {{ beer.abv }}</p>
  </article>
</template>

<script>
export default {
  name: 'beer-detail',
  props: ['beer']
}
</script>

<style lang="css" scoped>
</style>
