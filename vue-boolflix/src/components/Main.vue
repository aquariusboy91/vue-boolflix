<template>
  <div class="container">

       <div class="row">

        <Filmcards
        v-for="(card, index) in cards"
        :key="index"
        :title="card.title"
        :originaltitle="card.original_title"
        :lingua="card.original_language"
        :voto="card.vote_average"
        :nometv="card.name"
        :nometvoriginale="card.original_name"
        :img="card.poster_path"
      />

      <TvSeriescards 
        v-for="(cardtv, index) in tvcards"
        :key=" 'TV' + index"
        :lingua ="cardtv.original_language"
        :voto="cardtv.vote_average"
        :nometv="cardtv.name"
        :nometvoriginale="cardtv.original_name"
        :img="cardtv.poster_path"/>
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
    TvSeriescards
}

    }
  

</script>

<style>

</style>