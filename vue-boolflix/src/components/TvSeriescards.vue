<template>
    <div class="container">
        <h1>Tv Series </h1>
        <img
            class="rounded-circle shadow mb-3"
        >
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
    'nometvoriginale'

  ],

}
</script>

<style>

</style>