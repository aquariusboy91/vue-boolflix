<template>
  <div class="container">
      Boolflix
      <Search
            @doSearch="$emit('searchCall', ($event))"
          />
        
  </div>
  
</template>

<script>
import Search from './Search.vue';
export default {
    name: 'Header',
    components: {
    Search
  },
};

</script>

<style lang="scss" scoped>

</style>