<script setup>
  import Navbar from './components/Navbar.vue';


</script>

<template>

  <Navbar />
  <div class="bg-temporary"></div>
  <div class="mama">dasdasd</div>

</template>

<style scoped>
.bg-temporary {
  height: 100vh;
  position: relative;
  background-image: url(../src/assets/app/backgrounds/home-bg.jpeg);
  background-size: cover;
}

.mama {
  height: 1000px;
}

</style>
