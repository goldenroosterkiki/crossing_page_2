<template>
  <footer>
    <div class="footer-content">
      <div class="footer-left">
        <img :src="logo" alt="Logo" class="footer-logo" />
        <p class="copyright">Copyright © 2025 Crossing y Asuntos Públicos.</p>
      </div>
      <div class="footer-right">
        <ul>
          <li><a href="https://www.facebook.com/CrossingyAsuntosPublicos/">Facebook</a></li>
          <li><a href="https://x.com/CrossingyAP/">X (Twitter)</a></li>
          <li><a href="https://mx.linkedin.com/company/crossingyap/">LinkedIn</a></li>
        </ul>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue';

// Import the logo from the assets folder
const logo = ref(new URL('../assets/logo_bi.png', import.meta.url).href);
</script>

<style scoped>
/* Base Styles */
footer {
  background-color: #E4DDD3;
  padding: 40px 20px;
  color: black;
  text-align: center;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  max-width: 1200px; /* Optional: to limit the maximum width */
  margin: 0 auto; /* Center the footer content */
}

.footer-left,
.footer-right {
  flex: 1 1 300px; /* Allow flexibility and set a base width */
  padding: 10px;
}

.footer-left {
  display: flex;
  flex-direction: column;
  align-items: center; /* Center align on all screens */
  text-align: center;
  margin-bottom: 20px;
}

.footer-logo {
  max-width: 100%;
  height: auto;
  width: 120px; /* Base width, adjust as needed */
  margin-bottom: 10px;
}

.copyright {
  font-weight: 200;
}

.footer-right {
  display: flex;
  justify-content: center;
}

.footer-right ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  gap: 15px; /* Space between links */
}

.footer-right li {
  margin: 0;
}

.footer-right a {
  color: black;
  text-decoration: none;
  font-weight: 500;
}

.footer-right a:hover {
  text-decoration: underline;
}

/* Responsive Styles */
@media (max-width: 768px) {
  .footer-content {
    flex-direction: column;
    align-items: center;
  }

  .footer-left,
  .footer-right {
    flex: 1 1 100%;
    padding: 10px 0;
  }

  .footer-logo {
    width: 90px; /* Smaller logo on mobile */
  }

  .footer-right ul {
    flex-direction: column;
    align-items: center;
    gap: 10px;
  }
}

@media (max-width: 480px) {
  .footer-logo {
    width: 70px; /* Even smaller logo on very small screens */
  }

  footer {
    padding: 20px 10px;
  }

  .footer-right ul {
    gap: 8px;
  }

  .footer-right a {
    font-size: 14px;
  }
}
</style>
