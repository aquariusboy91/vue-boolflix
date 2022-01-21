<template>
    <div class="container">
        <h1>Tv Series </h1>
        <div v-if="img == null"> {{alt}} </div>
       <img v-else :src="'https://image.tmdb.org/t/p/w185' + img" alt="">
        <h2>{{nometv}}</h2>
        <h3>{{nometvoriginale}}</h3>
        <span><i :class="(lingua == 'en') ? 'flag flag-united-states' : 'flag flag-' + lingua"></i></span>
        <span>{{Math.floor(voto / 2)}}</span>
    </div>
</template>

<script>
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

<style>

</style>