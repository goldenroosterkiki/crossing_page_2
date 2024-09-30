<template>
  <div class="ofrecemos">
    <h2>Industrias en las que servimos</h2>
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

const cards = ref([
  { id: 1, text: 'Tecnología', image: new URL('../assets/tecnologia.png', import.meta.url).href },
  { id: 2, text: 'Alimentos', image: new URL('../assets/alimentos.png', import.meta.url).href },
  { id: 3, text: 'Logística', image: new URL('../assets/logistica.png', import.meta.url).href },
  { id: 4, text: 'Finanzas', image: new URL('../assets/finanzas.png', import.meta.url).href },
  { id: 5, text: 'Agropecuario', image: new URL('../assets/maiz.png', import.meta.url).href },
  { id: 6, text: 'Energía', image: new URL('../assets/energia.png', import.meta.url).href },
]);
</script>

<style scoped>
.functionality-cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 0 20px;
  gap: 20px;
}

.card {
  flex: 0 0 calc(9% - 17px);
  max-width: calc(9% - 17px);
  min-width: 150px;
  border-radius: 10px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: #202020;
  transition: all 0.3s ease;
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

h2 {
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
}

.card img {
  max-width: 100%;
  max-height: 4em;
  object-fit: contain;
}

@media (max-width: 1200px) {
  .card {
    flex: 0 0 calc(14% - 14px);
    max-width: calc(14% - 14px);
  }
}

@media (max-width: 768px) {
  .card {
    flex: 0 0 calc(25% - 10px);
    max-width: calc(25% - 10px);
    min-width: 0;
  }
}

@media (max-width: 480px) {
  .card {
    flex: 0 0 calc(25% - 10px);
    max-width: calc(25% - 10px);
    min-width: 0;
  }

  .functionality-cards {
    padding: 0 10px;
  }
}
</style>
