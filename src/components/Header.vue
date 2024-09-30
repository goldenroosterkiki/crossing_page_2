<template>
  <div class="header-container">
    <Navbar />
    <HeaderContent />
  </div>
</template>

<script setup>
import Navbar from './Navbar.vue';
import HeaderContent from './HeaderContent.vue';
</script>

<style scoped>
.header-container {
  display: flex;
  flex-direction: column;
  background-image: url('../assets/background.jpg');
  background-size: cover; /* Adjust based on your preference */
  background-repeat: no-repeat; /* Adjust based on your preference */
  background-position: center; /* Adjust based on your preference */
}
</style>
