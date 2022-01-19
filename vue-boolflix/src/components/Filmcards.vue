<template>
    <div class="container">
        <img
            class="rounded-circle shadow mb-3"
            :src="image"
            :alt="title"
        >
        <h2>{{title}}</h2>
    </div>
</template>

<script>
export default {
    name: 'Filmcards',
    props: [
    'image',
    'title',
  ],

}
</script>

<style>

</style>