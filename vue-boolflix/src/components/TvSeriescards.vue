<template>
    <div class="container">
        <div v-if="img == null"> {{alt}} </div>
       <img v-else :src="'https://image.tmdb.org/t/p/w185' + img" alt="">
        <h2>{{nometv}}</h2>
        <h3>{{nometvoriginale}}</h3>
        <span><i :class="(lingua == 'en') ? 'flag flag-united-states' : 'flag flag-' + lingua"></i></span>
        <span>{{Math.floor(voto / 2)}}</span>
        <!-- v-for in range da n a 5 con ternario per aggiunta delle classi -->
        <i
            v-for="n in 5"
            :key="n"
            :class="(n <= Math.floor(voto / 2)) ? 'fas fa-star' : 'far fa-star'"
          />
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
    'lingua',
    'voto',
    'nometv',
    'nometvoriginale',
    'img',
    'alt'

  ],

}
</script>

<style lang="scss">
@import '@fortawesome/fontawesome-free';

</style>