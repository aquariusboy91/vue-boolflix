<template>
    <div class="container">
        <img
            class="rounded-circle shadow mb-3"
        >
        <h2>{{title}} {{nometv}}</h2>
        <h3>{{originaltitle}} {{nometvoriginale}}</h3>
        <span>{{lingua}}</span>
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