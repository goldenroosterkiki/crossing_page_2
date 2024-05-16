<template>
  <footer>
    <div class="footer-content">
      <div class="footer-left">
        <img :src="logo" alt="Logo" class="footer-logo" />
        <p class="copyright">Copyright © 2024 Iurexa. All rights reserved.</p>
      </div>
      <div class="footer-right">
        <ul>
          <li><a href="#">About Us</a></li>
          <li><a href="#">Contact</a></li>
          <li><a href="#">Jobs</a></li>
          <li><a href="#">Get Started</a></li>
          <li><a href="#">X (Twitter)</a></li>
          <li><a href="#">LinkendIn</a></li>
          <li><a href="#">Blog</a></li>
        </ul>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue';

// Import the logo from the assets folder
const logo = ref(new URL('../assets/iurexa_logo.svg', import.meta.url).href);
</script>

<style scoped>
/* Add any styles for Footer.vue here */
footer {
  background-color: #000;
  padding: 40px 20px;
  color: white;
  text-align: center;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}

.copyright {
  font-weight: 200;
}

.footer-left {
  flex: 1;
  text-align: center;
  margin-bottom: 20px;
  padding: 0 10vh;
}

.footer-logo {
  max-width: 200px;
  margin-bottom: 10px;
}

.footer-right {
  flex: 1;
  text-align: center;
  padding: 0 10vh;
}

.footer-right ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-right li {
  margin: 10px 0;
}

.footer-right a {
  color: white;
  text-decoration: none;
}

.footer-right a:hover {
  text-decoration: underline;
}
</style>
