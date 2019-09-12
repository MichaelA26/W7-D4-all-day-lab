<template>
  <h1>Beerboys Never say Die!!!</h1>
</template>

<script>
export default {
}
</script>

<style lang="css" scoped>
</style>


<script>


export default {
  name: 'app',
  data(){
    return {
      beers: [],
      selectedBeer: null
    };
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)
  }


}
</script>

<style>

</style>
