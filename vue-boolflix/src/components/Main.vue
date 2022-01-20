<template>
  <div class="container">

       <div class="row">

          <!-- <Search
            @doSearch="searchFilms($event)"
          />
        </div> -->

        <Filmcards
        v-for="(card, index) in cards"
        :key="index"
        :title="card.title"
        :originaltitle="card.original_title"
        :lingua="card.original_language"
        :voto="card.vote_average"
      />
  </div>
  </div>
</template>

<script>
// import axios from 'axios';
import Filmcards from './Filmcards.vue';
export default {
    name: 'Main',
    props:{
      cards: {
        // type: Array,
        // default () {
        //         return [];
        //     },
      }
    },
    components: {
    Filmcards,
},
// data() {
//     return {
//       textSearch: '',
//       cards: null,
//       queryApiDeck: 'https://api.themoviedb.org/3/search/movie',
//       randomFilms: 'https://api.themoviedb.org/3/discover/movie?api_key=ccaa991275d1b8e7a1d986fa743c9cf2&language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_watch_monetization_types=flatrate'
//     };
//   },
  
//    methods: {
//        searchFilms(text) {
//            if(text == '') {
//                axios.get('https://api.themoviedb.org/3/discover/movie?api_key=ccaa991275d1b8e7a1d986fa743c9cf2&language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_watch_monetization_types=flatrate')
//             .then(results => {
//               this.cards = results.data.results;
//             })
//            } else if (text != ''){
//                 this.textSearch = text;
//                 console.log(this.textSearch)
//                 this.CallAxios()
//            }
//     },
//     CallAxios () {
//             axios.get(this.queryApiDeck, {
//             params: {
//               api_key: 'ccaa991275d1b8e7a1d986fa743c9cf2',
//               query: this.textSearch
//           }
//       })
//         .then(results => {
//           console.log(results);
//           this.cards = results.data.results
//         })
//         .catch((error) => {
//           console.log(error);
//         });
        
//     }
//    }

    }
  

</script>

<style>

</style>