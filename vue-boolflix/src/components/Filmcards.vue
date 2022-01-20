<template>
    <div class="container">
        <h1>Film</h1>
        <img :src="'https://image.tmdb.org/t/p/w185' + img" alt="">
        <h2>{{title}} {{nometv}}</h2>
        <h3>{{originaltitle}} {{nometvoriginale}}</h3>
        <span><i :class="(lingua == 'en') ? 'flag flag-united-states' : 'flag flag-' + lingua"></i></span>
        <span>{{voto}}</span>
    </div>
</template>

<script>
export default {
    name: 'Filmcards',
    props: [
    'title',
    'originaltitle',
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