<template lang="html">
  <article v-if="beer">
    <p>Name: {{ beer.name }}</p>
    <p>Tagline: {{ beer.tagline }}</p>
    <p>A wee description: {{ beer.description }}</p>
    <p>ABV: {{ beer.abv }}</p>
    <div class="img-container">
      <img class="brewskiimg" v-bind:src="beer.image_url" alt="Broken. Gosh Darn it!">
    </div>
  </article>
</template>

<script>
export default {
  name: 'beer-detail',
  props: ['beer']
}
</script>

<style lang="css" scoped>

.brewskiimg{
  height: 200px;
}

.image-container{
  display: flex;
  align-content: center;
  align-self: center;
}

p {
  text-align: center;
}


</style>
