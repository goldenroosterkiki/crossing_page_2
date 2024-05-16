<template>
    <div class="functionality-cards" id="functionality-cards">
      <div class="card" v-for="card in cards" :key="card.id">
        <div class="card-text">
          <p class="actual-text">{{ card.text }}</p>
        </div>
        <div class="card-image">
          <img :src="card.image" alt="Illustration" />
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  // Placeholder data for the cards
  const cards = ref([
    { id: 1, text: '1. We reason and breakdown the user request', image: new URL('../assets/reason.svg', import.meta.url).href },
    { id: 2, text: '2. We teach agents to navigate custom data maps', image: new URL('../assets/navigation.svg', import.meta.url).href },
    { id: 3, text: '3. We Select the best pieces of information for your task', image: new URL('../assets/docs.svg', import.meta.url).href },
  ]);
  </script>
  
  <style scoped>
  /* Add any styles for FunctionalityCards.vue here */
  .functionality-cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    padding: 0 20vh;
  }
  
  .card {
    background: linear-gradient(180deg, rgba(8,12,16,1) 0%, rgba(14,14,15,1) 100%);
    border-radius: 10px;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    width: 20%;
    text-align: center;
    color: white;
    transition: all 0.3s ease;
  }

  .card:hover {
    border-radius: 30px;
  }
  
  .card-text {
    margin-bottom: 20px;
  }

  .actual-text {
    font-weight: 200;
  }
  
  .card img {
    max-width: 100%;
    height: 7em;
  }
  
  @media (max-width: 768px) {
    .card {
      width: 80%;
    }

    .functionality-cards {
    padding: 0 3vh;
    gap: 3vh;
  }
  }
  </style>
  