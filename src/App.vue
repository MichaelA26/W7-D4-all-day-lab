<template>
  <div>
    <h1>Beerboys Never say Die!!!</h1>
    <beer-detail :beer='selectedBeer'></beer-detail>
    <beers-list :beers='beers'></beers-list>
  </div>
</template>

<script>
import ListComponent from './components/ListComponent.vue';
import BeersList from './components/BeersList.vue';
import BeerDetail from './components/BeerDetail.vue';
import {eventBus} from './main.js'

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
    .then(beers => {
      beers.forEach(beer => {
        beer.favourited = false
      })
      this.beers = beers
    })

    eventBus.$on('beer-selected', (beer) => {
      this.selectedBeer = beer
    })

    eventBus.$on('beer-favourited', (beer) => {
      console.log("yo")
      if (beer.favourited === false) {
        beer.favourited = true
      }
      else {
        beer.favourited = false
      }
    })
  },

  components: {
    "beers-list": BeersList,
    "beer-detail": BeerDetail
  }

}
</script>

<style>

body {
  color: yellow;
  background-color: black;
  background-image: url(../public/beerBoys_S.jpg);
  background-size: cover;
  background-repeat: no-repeat;
}

p {
  background-color: black;
  color: yellow;
}

h1 {
  text-align: center;
  text-shadow: 1px 1px 1px black;
  color: yellow;
  background-color: black;
}

ul {
  color: yellow;
  background-color: black;
  display: inline;
  text-align: center;
}

li {
  display: inline;
  color: yellow;
  background-color: black;
}

button {
  display: inline;
}

</style>
