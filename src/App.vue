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
    .then(beers => this.beers = beers)

    eventBus.$on('beer-selected', (beer) => {
      this.selectedBeer = beer
    })
  },

  components: {
    "beers-list": BeersList,
    "beer-detail": BeerDetail
  }

}
</script>

<style>

</style>
