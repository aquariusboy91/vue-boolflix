<template>
  <div class="container">

       <div class="row">

          <Search
            @doSearch="searchFilms($event)"
          />
        </div>

        <Filmcards
        v-for="(card, index) in cards"
        :key="index"
        :title="card.title"
        :originaltitle="card.original_title"
        :lingua="card.original_language"
        :voto="card.vote_count"
      />
  </div>
</template>

<script>
import axios from 'axios';
import Filmcards from './Filmcards.vue';
import Search from './Search.vue';
export default {
    name: 'Main',
    components: {
    Filmcards,
    Search,
},
data() {
    return {
        ciao : '',
      textSearch: '',
      cards: null,
      queryApiDeck: 'https://api.themoviedb.org/3/search/movie',
    };
  },
   methods: {
       searchFilms(text) {
         this.textSearch = text;
        console.log(this.textSearch)
        this.CallAxios()
    },
  
    CallAxios () {
      axios.get(this.queryApiDeck, {
          params: {
              api_key: 'ccaa991275d1b8e7a1d986fa743c9cf2',
              query: this.textSearch
          }
      })
        .then(results => {
          console.log(results);
          this.cards = results.data.results
        })
        .catch((error) => {
          console.log(error);
        });
    }
   }

    }
  

</script>

<style>

</style>