<template>
  <div class="container">
      Boolflix
      <Search
            @doSearch="$emit(searchFilms($event))"
          />
        
  </div>
  
</template>

<script>
import Search from './components/Search.vue';
export default {
    name: 'Header',
    components: {
    Search
  },
};

</script>

<style lang="scss" scoped>

</style>