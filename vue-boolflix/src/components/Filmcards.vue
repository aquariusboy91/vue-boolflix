<template>
    <div class="container">
        <h1>Film</h1>
        <img
            class="rounded-circle shadow mb-3"
        >
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
    'nometvoriginale'

  ],

}
</script>

<style>

</style>