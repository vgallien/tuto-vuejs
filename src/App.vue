<template>
  <div id="app">
    <header-top></header-top>
    <todo></todo>
    <!-- <contenu></contenu> -->
  </div>
</template>

<script>

// import Contenu from './components/Contenu.vue'
import Header from './components/Header.vue'
import ToDo from './components/ToDo/ToDo'

export default {
  name: 'App',
  components: {
    // 'contenu': Contenu,
    'header-top': Header,
    'todo': ToDo
  }
}
</script>

<style>

</style>
