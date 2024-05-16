<template>
  <div class="contact-container">
    <div class="contact-card" id="contact-card">
      <!-- Placeholder content for ContactCard.vue -->
      <p class="onboarding-text">We are onboarding early testers and partners. Be one of them!</p>
      <p class="email-text">info@iurexa.com</p>
    </div>
  </div>
</template>

<script setup>
// Add any script setup logic here if needed
</script>

<style scoped>
.contact-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  text-align: center;
}

/* Add any styles for ContactCard.vue here */
.contact-card {
  padding: 20px;
  background: linear-gradient(180deg, rgba(8,12,16,1) 0%, rgba(14,14,15,1) 100%);
  border-radius: 10px;
  text-align: center;
  max-width: 50%;
  padding: 10vh;
}

h2 {
  margin: 0 0 10px;
}

p {
  margin: 0;
}

.onboarding-text {
  font-size: 1.5em;
  font-weight: 200;
  margin-bottom: 3vh;
}

.email-text {
  font-size: 1.7em;
  font-weight: 400;
}

@media (max-width: 768px) {
  .onboarding-text {
  font-size: 1em;
  font-weight: 200;
  margin-bottom: 3vh;
}

.email-text {
  font-size: 1.2em;
  font-weight: 400;
}
  }
</style>
