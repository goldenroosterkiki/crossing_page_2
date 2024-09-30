<template>
  <section class="team-section" id="team-section">
    <div class="team-card">
      <h2>Nuestro Equipo</h2>
      <p>
        Somos un equipo de profesionistas mexicanos con amplia experiencia en Gobierno,
        Legislación, Iniciativa Privada y Academia. Nos enfocamos en ofrecer soluciones a
        través de la construcción de escenarios, así como en el procesamiento y análisis de datos públicos usando tecnología avanzada
        como bases de datos y software especializado.
      </p>
    </div>
  </section>
</template>

<script setup>
// No additional script is needed for this component
</script>

<style scoped>
.team-section {
  display: flex;
  justify-content: center;
  padding: 20px;
}

.team-card {
  max-width: 800px;
  background-color: #C6C6C6;
  border-radius: 8px;
  padding: 3em;
  color: #202020;
}

.team-card h2 {
  font-family: 'Space Grotesk', sans-serif;
  font-weight: 500;
  font-size: 2em;
  margin-bottom: 20px;
}

.team-card p {
  font-family: 'Space Grotesk', sans-serif;
  font-weight: 300;
  font-size: 1.2em;
  line-height: 1.5;
}

/* Responsive adjustments */
@media (max-width: 600px) {
  .team-card {
    padding: 15px;
  }
  .team-card h2 {
    font-size: 1.5em;
  }
  .team-card p {
    font-size: 1em;
  }
}
</style>
