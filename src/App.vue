<script>
import { RouterView } from 'vue-router'
import Navbar from './components/Navbar.vue'

export default {
  components: {
    Navbar
  }
}
</script>

<template>
  <Navbar/>
  <RouterView />
</template>

<style>
@import '@/assets/css/styles.css';

.nav-link.router-link-active {
  color: rgb(79, 70, 229) !important
}
nav {
  position: sticky;
  top: 0;
  z-index: 99;
}
</style>
