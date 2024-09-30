<template>
  <section class="product-section" id="product-section">
    <div class="product-card">
      <h2>Ketza AI</h2>
      <p>
        Ahora tranformamos miles de datos en instantáneos reportes detallados y accionables gracias a nuestro propio producto de Inteligencia Artificial.
      </p>
      <div class="features">
        <div class="feature-card">
          <div class="icon">🔎</div>
          <h3>Búsqueda Profunda</h3>
        </div>
        <div class="feature-card">
          <div class="icon">🚀</div>
          <h3>Analisis en Minutos</h3>
        </div>
        <div class="feature-card">
          <div class="icon">💡</div>
          <h3>Identificación de Oportunidades</h3>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// No additional script is needed for this component
</script>

<style scoped>
.product-section {
  position: relative;
  overflow: hidden;
  padding: 20px;
  border-radius: 2em;
}

.product-card {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
  padding: 3em;
  color: #202020;
  backdrop-filter: blur(5px);
}

.product-card h2 {
  font-family: 'Space Grotesk', sans-serif;
  font-weight: 500;
  font-size: 2em;
  margin-bottom: 20px;
}

.product-card p {
  font-family: 'Space Grotesk', sans-serif;
  font-weight: 300;
  font-size: 1.2em;
  line-height: 1.5;
}

.features {
  display: flex;
  justify-content: space-around;
  margin-top: 2em;
}

.feature-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 1em;
  background: #ECECEC;
  border-radius: 8px;
  width: 10em;
}

.feature-card .icon {
  font-size: 3em;
  margin-bottom: 0.5em;
}

.feature-card h3 {
  font-family: 'Space Grotesk', sans-serif;
  font-weight: 400;
  font-size: 1.1em;
}

/* Background Animation */
.product-section::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background-image: linear-gradient(45deg, #f3ec78, #af4261, #F2C577, #af4261);
  background-size: 400% 400%;
  animation: gradientBG 7s ease infinite;
  z-index: -1;
}

@keyframes gradientBG {
  0% {background-position: 0% 50%;}
  50% {background-position: 100% 50%;}
  100% {background-position: 0% 50%;}
}

/* Responsive adjustments */
@media (max-width: 600px) {
  .features {
    flex-direction: column;
    align-items: center;
  }
  .feature-card {
    width: 80%;
    margin-bottom: 1em;
  }
  .product-card {
    padding: 0;
  }
}

@media (max-width: 600px) {
  .product-card h2 {
    font-size: 1.5em; /* Reduce font size for h2 */
  }
  .product-card p {
    font-size: 1em; /* Reduce font size for paragraph */
  }
  .feature-card h3 {
    font-size: 0.9em; /* Reduce font size for feature titles */
  }
  .feature-card .icon {
    font-size: 2.5em; /* Reduce icon size */
  }
}


</style>
