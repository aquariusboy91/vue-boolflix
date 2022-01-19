<template>
    <div class="container">
        <img
            class="rounded-circle shadow mb-3"
        >
        <h2>{{title}}</h2>
        <h3>{{originaltitle}}</h3>
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
    'voto'
  ],

}
</script>

<style>

</style>