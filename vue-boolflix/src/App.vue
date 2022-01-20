<template>
  <div id="app">
    <Header
      @searchCall="searchFilms($event)"/>
    <Main 
      :cards="cards"
      :tvcards="tvcards"/>
  </div>
</template>

<script>
import axios from 'axios'
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: "App",
  components: {
    Header,
    Main
  },
  data() {
    return {
      textSearch: '',
      cards: null,
      tvcards:null,
      queryApiDeck: 'https://api.themoviedb.org/3/search/movie',
      randomFilms: 'https://api.themoviedb.org/3/discover/movie?api_key=ccaa991275d1b8e7a1d986fa743c9cf2&language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_watch_monetization_types=flatrate',
      queryApiDeckTv: 'https://api.themoviedb.org/3/search/tv?api_key=ccaa991275d1b8e7a1d986fa743c9cf2&language=it_IT'
    };
  },
  
   methods: {
       searchFilms(text) {
           if(text == '') {
               axios.get('https://api.themoviedb.org/3/discover/movie?api_key=ccaa991275d1b8e7a1d986fa743c9cf2&language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_watch_monetization_types=flatrate')
            .then(results => {
              this.cards = results.data.results;
            })
           } else if (text != ''){
                this.textSearch = text;
                console.log(this.textSearch)
                this.CallAxios()
           }
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
        })
         axios.get(this.queryApiDeckTv, {
          params: {
          query: this.textSearch
        }
      })
      .then(results => {
        console.log(results);
        this.tvcards = results.data.results
      })
      .catch((error) => {
          console.log(error);
        });
    },
   }
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import '~mdb-ui-kit/css/mdb.min.css';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
