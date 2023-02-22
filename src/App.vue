<script>

import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import HandlingUserImport from './components/HandlingUserInput.vue'

import DemoGrid from './components/Grid.vue'
import AttributeBindings from './components/AttributeBindings.vue'
 
 export default {
    components: {
    DemoGrid,
    HandlingUserImport,
    AttributeBindings
  },      
  data: () => ({
    searchQuery: '',
    gridColumns: ['name', 'power'],
    gridData: [
      { name: 'Chuck Norris', power: Infinity },
      { name: 'Bruce Lee', power: 9000 },
      { name: 'Jackie Chan', power: 7000 },
      { name: 'Jet Li', power: 8000 }
    ]
  })
} 

</script>

<template>
  <header><!-- 
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

    </div> -->
  </header>
  
  <div id="grid-sort-filter" style="width:100%;">
    <h2>An example of grid with sort and filter</h2>
      <form id="search">
        Search <input name = "query" v-model="searchQuery">
      </form>
      <DemoGrid
        :data = "gridData"
        :columns = "gridColumns"
        :filter-key = "searchQuery">
      </DemoGrid>
      <HandlingUserImport></HandlingUserImport>
      <AttributeBindings></AttributeBindings>

  </div>
  <!-- <RouterView /> -->
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
