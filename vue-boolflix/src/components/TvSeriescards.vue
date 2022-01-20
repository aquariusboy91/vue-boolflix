<template>
    <div class="container">
        <h1>Tv Series </h1>
       <img :src="'https://image.tmdb.org/t/p/w342' + img" alt="">
        <h2>{{nometv}}</h2>
        <h3>{{nometvoriginale}}</h3>
        <span><i :class="(lingua == 'en') ? 'flag flag-united-states' : 'flag flag-' + lingua"></i></span>
        <span>{{voto}}</span>
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
    'img'

  ],

}
</script>

<style>

</style>