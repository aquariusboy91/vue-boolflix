<template>
  <div class="container-fluid bg-movie">
        <h2>Movies</h2>
       <div class="row row-cols-6 ">

        <Filmcards
        v-for="(card, index) in cards"
        :key="index"
        :title="card.title"
        :originaltitle="card.original_title"
        :lingua="card.original_language"
        :voto="card.vote_average"
        :img="card.poster_path"
        :alt="card.title"
        :descr="card.overview"
      />
      </div>
       <h2>Tv Series</h2>
       <div class="row row-cols-6 ">
        <TvSeriescards 
          v-for="(cardtv, index) in tvcards"
          :key=" 'TV' + index"
          :lingua ="cardtv.original_language"
          :voto="cardtv.vote_average"
          :nometv="cardtv.name"
          :nometvoriginale="cardtv.original_name"
          :img="cardtv.poster_path" 
          :alt="cardtv.name"
          />
        </div>
  </div>
</template>

<script>
// import axios from 'axios';
import Filmcards from './Filmcards.vue';
import TvSeriescards from './TvSeriescards.vue';
export default {
    name: 'Main',
    props:{
      cards: {
        // type: Array,
        // default () {
        //         return [];
        //     },
      },
      tvcards: {

      }
    },
    components: {
    Filmcards,
    TvSeriescards,
}

    }
  

</script>

<style lang="scss" scoped>
    h2 {
      color: white;
      margin-top: 0.5em;
      margin-bottom: 0.5em;
    }
  

</style>