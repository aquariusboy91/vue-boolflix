<template>
  <div class="search">
    <input
      id="search"
      v-model="inputText"
      type="text"
      name="search"
    >
    <button
      class="btn btn-danger color-button"
      type="submit"
      @click="$emit('doSearch', inputText)"
    >
      Search
    </button>
  </div>
</template>

<script>
export default {
  name: 'Search',
  data() {
    return {
      inputText: '',
    };
  },
};
</script>

<style lang="scss">
 .btn.btn-danger {
   background-color: #c90d16;
   color: white;
   padding: 2px 6px;
   font-size: 13px;
   margin-left: 0.5em;
   vertical-align: 0.1em;
 }
 input {
   height: 1.6em;

 }


</style>