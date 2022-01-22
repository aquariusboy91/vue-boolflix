<template>
    <div class="card-cont bg-movie">
        <div class="alt" v-if="img == null"> {{alt}} </div>
        <img v-else :src="'https://image.tmdb.org/t/p/w185' + img" alt="" v-on:click="info()" class="img-movie">
        <div :class= "{active: isactive}" class="info-card">
            <h3>{{title}}</h3>
            <p>{{descr}}</p>
            <!-- <h3>{{originaltitle}} {{nometvoriginale}}</h3> -->
            <span class="flag"><i :class="(lingua == 'en') ? 'flag flag-united-states' : 'flag flag-' + lingua"></i></span>
            <!-- <span>{{Math.floor(voto / 2)}}</span> -->
            <!-- v-for in range da n a 5 con ternario per aggiunta delle classi -->
            <i
                v-for="n in 5"
                :key="n"
                :class="(n <= Math.floor(voto / 2)) ? 'fas fa-star' : 'far fa-star'"
            />
          </div>
    </div>
</template>

<script>
import { faStar } from '@fortawesome/free-solid-svg-icons'
import { library } from '@fortawesome/fontawesome-svg-core'
import '@fortawesome/fontawesome-free/css/all.css';
library.add(faStar)
export default {
    name: 'Filmcards',
    props: [
    'title',
    'originaltitle',
    'lingua',
    'voto',
    'nometv',
    'nometvoriginale',
    'img',
    'alt',
    'descr'
    ],
  data() {
      return {
          isactive: false
         
      }
  },
  methods: {
    info() {
      this.isactive = !this.isactive;
      console.log(this.isactive)
    }
  }
}
</script>

<style lang="scss">
@import '@fortawesome/fontawesome-free';
    .bg-movie {
        background-color: #141414;
    }
    .img-movie { 
      padding: 0 2px;
      transition-duration: 0.4s;
      padding-bottom: 0.7em;
      
      &:hover { 
        margin: 0 7px;
        transform: scale(1.1);
      }
    }
    .info-card {
        display: none;
        color: white;

    }    

    .active {
        display: inline;
        
    }


    .fas.fa-star {
        color: yellow
    }
    .alt {
        color:white;
    }
    p {
        color: white;
        font-size: 10px;
    }

</style>