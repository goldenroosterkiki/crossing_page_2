<template>
  <div class="ofrecemos">
    <h2>Ofrecemos una visión integral de los asuntos públicos en los poderes:</h2>
  </div>
  <div class="functionality-cards" id="functionality-cards">
    <div class="card" v-for="card in cards" :key="card.id">
      <div class="card-image">
        <img :src="card.image" alt="Illustration" />
      </div>
      <div class="card-text">
        <p class="actual-text">{{ card.text }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
  import { ref } from 'vue';

  // Placeholder data for the cards
  const cards = ref([
    { id: 1, text: 'Legislativo', image: new URL('../assets/cabildeo.png', import.meta.url).href },
    { id: 2, text: 'Ejecutivo', image: new URL('../assets/politicos.png', import.meta.url).href },
    { id: 3, text: 'Judicial', image: new URL('../assets/monitoreo.png', import.meta.url).href },
  ]);
</script>

  
<style scoped>
.functionality-cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 0 20vh;
}

.card {
  background: #D4D4D4;
  border-radius: 10px;
  border: 2px solid #253743;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center; /* Centers content vertically */
  align-items: center;
  width: 17%;
  text-align: center;
  color: #202020;
  transition: all 0.3s ease;
  height: 180px; /* Fixed height for all cards */
}

.card:hover {
  border-radius: 30px;
}

.card-image {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
}

.card-text {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 500;
  font-family: 'Space Grotesk', sans-serif;
}

h2, h3 {
  font-family: 'Space Grotesk', sans-serif;
  color: #202020;
}

.ofrecemos {
  text-align: center;
  align-items: center;
  justify-content: center;
}

.actual-text {
  font-weight: 300;
  font-size: 1.1em;
}

.card img {
  max-width: 100%;
  max-height: 6.5em;
  object-fit: contain;
}

/* Mobile Styles */
@media (max-width: 768px) {
  .functionality-cards {
    padding: 0 3vh;
    gap: 2vh; /* Reduced gap for tighter layout */
  }

  .card {
    width: 90%; /* Reduced width for smaller cards */
    padding: 10px; /* Less padding for compactness */
    height: 150px; /* Decreased height */
  }

  .actual-text {
    font-size: 1em; /* Slightly smaller font size */
  }

  .card img {
    max-height: 4em; /* Smaller image size */
  }
}
</style>

  
  