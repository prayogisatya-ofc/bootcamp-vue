<script setup>
import { RouterView } from 'vue-router'
import Navbar from './components/Navbar.vue'
</script>

<template>
  <Navbar/>
  <RouterView />
</template>

<style>
@import '@/assets/css/styles.css';

.router-link-active {
  color: rgb(79, 70, 229) !important
}
</style>
