<template>
  <main>
    <!-- Placeholder content for BodyContent.vue -->
    <FunctionalityCards />
    <FeaturesCards />
    <ContactCard />
  </main>
</template>

<script setup>
import FunctionalityCards from './FunctionalityCards.vue';
import FeaturesCards from './FeaturesCards.vue';
import ContactCard from './ContactCard.vue';
</script>

<style scoped>
/* Add any styles for BodyContent.vue here */
main {
  color: aliceblue;
  display: flex;
  flex-direction: column;
  gap: 20px;
  padding: 20px;
  padding-top: 0;
}
</style>
