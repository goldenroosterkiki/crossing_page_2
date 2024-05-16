<template>
  <div class="features-cards">
    <div v-for="(card, index) in cards" :key="index" :class="['card', card.type, `order-${index + 1}`]">
      <div v-if="card.type === 'image-card'" class="card-content">
        <img :src="card.image1" alt="Image 1" />
        <img :src="card.image2" alt="Image 2" />
      </div>
      <div v-else class="card-content">
        <p class="title-text">{{ card.title }}</p>
        <p class="paragraph-text">{{ card.text }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Placeholder data for the cards
const cards = ref([
  { type: 'image-card', image1: new URL('../assets/balanza.png', import.meta.url).href, image2: new URL('../assets/monedas.png', import.meta.url).href },
  { type: 'text-card', title: 'Specialization Domains', text: 'En un lugar de la Mancha, de cuyo nombre no quiero acordarme, no ha mucho tiempo que vivía un hidalgo.' },
  { type: 'text-card', title: 'For Enterprise', text: 'En un lugar de la Mancha, de cuyo nombre no quiero acordarme, no ha mucho tiempo que vivía un hidalgo' },
  { type: 'image-card', image1: new URL('../assets/cohete.png', import.meta.url).href, image2: new URL('../assets/edificio.png', import.meta.url).href },
  { type: 'image-card', image1: new URL('../assets/mac.png', import.meta.url).href, image2: new URL('../assets/cloud.png', import.meta.url).href },
  { type: 'text-card', title: 'Store it Locally!', text: 'En un lugar de la Mancha, de cuyo nombre no quiero acordarme, no ha mucho tiempo que vivía un hidalgo' },
]);
</script>

<style scoped>
.features-cards {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  padding: 10vh 20vh;
}

.card {
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin: 5vh 0;
}

.image-card {
  background: linear-gradient(180deg, rgba(8,12,16,1) 0%, rgba(33,47,62,1) 100%);
  border-radius: 2em;
  text-align: center;
}

.text-card {
  background-color: #000;
  border-radius: 0;
  text-align: left;
}

.card-content {
  padding: 20px;
}

.title-text {
  font-size: 1.4em;
  font-weight: 500;
}

.paragraph-text {
  font-size: .9em;
  font-weight: 300;
}

.image-card img {
  max-height: 7em;
  width: auto;
  margin: 10px;
  padding: 0 3vh;
}

@media (max-width: 768px) {
  .features-cards {
    grid-template-columns: 1fr;
  }
  .order-1 { order: 1; }
  .order-2 { order: 2; }
  .order-3 { order: 4; } /* Changed order */
  .order-4 { order: 3; } /* Changed order */
  .order-5 { order: 5; }
  .order-6 { order: 6; }

  .features-cards {
  padding: 5vh 1vh;
}

.image-card img {
  max-height: 4.5em;
  width: auto;
  margin: 10px;
  padding: 0 2vh;
}

.card {
  margin: .5vh 0;
}

}
</style>
