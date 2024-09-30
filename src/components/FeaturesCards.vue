<template>
  <div class="features-cards" id="features-cards">
    <div
      v-for="(card, index) in cards"
      :key="index"
      :class="['card', card.type, `order-${index + 1}`]"
    >
      <div v-if="card.type === 'image-card'" class="card-content">
        <!-- Display only the first image -->
        <img :src="card.image1" alt="Image" />
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
  {
    type: 'image-card',
    image1: new URL('../assets/coyuntura.png', import.meta.url).href,
    // image2 is no longer needed; you can remove it if desired
  },
  {
    type: 'text-card',
    title: 'Análisis de coyuntura',
    text: 'Sirve para escrutar los acontecimientos de manera estructurada y responder a las preguntas clave: ¿qué?, ¿por qué? y ¿quién?, fortaleciendo la capacidad de nuestros clientes para anticipar cambios legislativos y de políticas públicas.',
  },
  {
    type: 'text-card',
    title: 'Vinculación',
    text: 'Estrategias y acciones para promover, defender o influir en las decisiones de los poderes públicos.',
  },
  {
    type: 'image-card',
    image1: new URL('../assets/vinculacion.png', import.meta.url).href,
    // image2 is no longer needed
  },
  {
    type: 'image-card',
    image1: new URL('../assets/analisis.png', import.meta.url).href,
    // image2 is no longer needed
  },
  {
    type: 'text-card',
    title: 'Seguimiento de cambios en el panorama político',
    text: 'Observamos puntualmente los cambios legislativos, económicos, políticos, electorales y regulatorios para analizarlos y dar una respuesta oportuna a nuestros clientes.',
  },
]);
</script>

<style scoped>
.features-cards {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  padding: 10vh 0;
}

.card {
  color: #202020;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin: 5vh 0;
}

.image-card {
  background: linear-gradient(
    90deg,
    rgba(228, 221, 211, 1) 0%,
    rgba(196, 196, 196, 1) 49%,
    rgba(228, 221, 211, 1) 100%
  );
  border-radius: 2em;
  text-align: center;
}

.text-card {
  background-color: #e4ddd3;
  border-radius: 0;
  text-align: left;
}

.card-content {
  padding: 20px;
}

.title-text {
  font-size: 1.4em;
  font-weight: 500;
  font-family: 'Space Grotesk', sans-serif;
}

.paragraph-text {
  font-size: 1em;
  font-weight: 300;
}

/* Style for the image on desktop */
.image-card img {
  height: 8em;
  width: auto;
  margin: 10px auto; /* Center the image horizontally */
  padding: 0 3vh;
  object-fit: contain; /* Ensures the image maintains aspect ratio */
}

@media (max-width: 768px) {
  .features-cards {
    grid-template-columns: 1fr;
    padding: 5vh 1vh;
  }

  .order-1 { order: 1; }
  .order-2 { order: 2; }
  .order-3 { order: 4; } /* Changed order */
  .order-4 { order: 3; } /* Changed order */
  .order-5 { order: 5; }
  .order-6 { order: 6; }

  .image-card img {
    height: auto;
    width: 100%;
    max-width: 20em;
    margin: 10px 0;
    padding: 0;
  }

  .card {
    margin: 0.5vh 0;
    justify-content: center;
  }
}
</style>
