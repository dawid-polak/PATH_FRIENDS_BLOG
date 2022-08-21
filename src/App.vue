<template>

  <Navbar />
  <router-view></router-view>
  <News/>

</template>

<script setup>
  import Navbar from './components/Navbar.vue'; 
  import News from './components/News.vue';

</script>

<style scoped>

</style>
