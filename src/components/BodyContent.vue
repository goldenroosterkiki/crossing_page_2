<template>
  <main>
    <FunctionalityCards />
    <IndustriesSection />
    <FeaturesCards />
    <Ketza />
    <Team />
    <ContactCard />
  </main>
</template>

<script setup>
import FunctionalityCards from './FunctionalityCards.vue';
import IndustriesSection from './Industries.vue';
import FeaturesCards from './FeaturesCards.vue';
import Ketza from './Ketza.vue'; 
import Team from './Team.vue'; 
import ContactCard from './ContactCard.vue';
</script>

<style scoped>
main {
  color: aliceblue;
  display: flex;
  flex-direction: column;
  gap: 20px;
  padding: 20px;
  padding-top: 0;
}
</style>
