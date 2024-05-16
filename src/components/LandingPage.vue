<template>
  <div>
    <HeaderContent />
    <BodyContent />
    <FooterContent />
  </div>
</template>

<script setup>
import HeaderContent from './Header.vue';
import BodyContent from './BodyContent.vue';
import FooterContent from './Footer.vue';
</script>

<style scoped>
/* Add any styles for LandingPage.vue here */
div {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
</style>