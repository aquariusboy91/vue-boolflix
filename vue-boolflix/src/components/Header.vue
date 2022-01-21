<template>
  <div class="container-fluid bg-header">

    <div class="row flex-nowrap align-items-center justify-content-between">

      <div class="logo-list">
          <img src="..\assets\img\netlogo.jpg" alt="" class="logo">
          <ul class="menu-list">
            <a href=""><li>Home</li></a>
            <a href=""><li>Tv Shows</li></a>
            <a href=""><li>Movies</li></a>
            <a href=""><li>Originals</li></a>
            <a href=""><li>Recently Added</li></a>
            <a href=""><li>Mylist</li></a>
          </ul>
      </div>

      <Search
            @doSearch="$emit('searchCall', ($event))"
            class="search"
          />

      </div>

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
  .logo {
    width: 120px;
    height: 50px;
    
  }
  .search {
    display: inline;
    width: 300px;
  }
  .bg-header {
    background-color: #000000;
  }
  .menu-list {
    list-style-type: none;
    width: 50%;
    margin-bottom: 0;
    
  }
    .menu-list a {
      text-decoration: none;
    }
    .menu-list li {
      display: inline;
      padding-right: 1em;
      color: white;
      font-size: 14px;
    }
    .logo-list {
          display: flex;
          align-items: center;
           width: 65%;
    }

</style>