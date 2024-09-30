<template>
    <nav class="navbar">
      <div class="logo">
        <!-- Placeholder for logo -->
        <img :src="logo" alt="Logo" />
      </div>
      <div class="burger" @click="toggleMenu">
        <!-- Burger icon -->
        <div :class="{'line': true, 'line1': true, 'open': menuOpen}"></div>
        <div :class="{'line': true, 'line2': true, 'open': menuOpen}"></div>
        <div :class="{'line': true, 'line3': true, 'open': menuOpen}"></div>
      </div>
      <transition name="menu">
        <div v-if="menuOpen || !isMobileView" class="menu-options">
          <!-- Placeholder for menu options -->
          <ul>
            <li><a href="https://crossing.ngrok.app/" target="_blank">Acceso Usuarios</a></li>
            <li><a href="#features-cards">Servicios</a></li>
            <li><a href="#team-section">Equipo</a></li>
            <li><a href="#contact-card">Contacto</a></li>
          </ul>
        </div>
      </transition>
    </nav>
  </template>
  
  <script setup>
  import { ref, onMounted, onUnmounted } from 'vue';
  
  // Import the logo from the assets folder
  const logo = ref(new URL('../assets/logo_text.png', import.meta.url).href);
  const menuOpen = ref(false);
  const isMobileView = ref(window.innerWidth <= 768);
  
  const toggleMenu = () => {
    menuOpen.value = !menuOpen.value;
  };
  
  const handleResize = () => {
    isMobileView.value = window.innerWidth <= 768;
    if (!isMobileView.value) {
      menuOpen.value = false; // Ensure menu is closed in desktop view
    }
  };
  
  onMounted(() => {
    window.addEventListener('resize', handleResize);
    handleResize();
  });
  
  onUnmounted(() => {
    window.removeEventListener('resize', handleResize);
  });
  </script>
  
  <style scoped>
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 2em;
    padding-left: 3.5em;
    padding-right: 3.5em;
    color: #9EB3B8;
    position: relative;
  }
  .logo img {
    height: 2.9em;
  }
  
  .burger {
    display: none;
    cursor: pointer;
    flex-direction: column;
    gap: 5px;
  }
  
  .line {
    width: 25px;
    height: 3px;
    background-color: #253743;
    transition: all 0.3s ease;
  }
  
  .line1.open {
    transform: rotate(45deg) translate(6px, 6px);
  }
  
  .line2.open {
    opacity: 0;
  }
  
  .line3.open {
    transform: rotate(-45deg) translate(5px, -5px);
  }
  
  .menu-options {
    border: 1px solid #253743;
    background-color: #143A54;
    border-radius: .8em;
    padding: 1em;
    display: flex;
    flex-direction: row;
    align-items: center;
    transition: all 0.3s ease;
  }

  .menu-options:hover {
    border-radius: 1.4em;
  }
  
  
  .menu-options ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    display: flex;
    gap: 3em;
  }
  
  .menu-options li {
    margin: 0;
  }

  .menu-options a:hover {
    color: #39668D;
  }
  
  .menu-options a {
    text-decoration: none;
    color: #E4DDD3;
    font-weight: 200;
    transition: all 0.3s ease;
    font-family: 'Space Grotesk', sans-serif;
  }
  
  @media (max-width: 768px) {
    .burger {
      display: flex;
    }
    .menu-options {
      position: absolute;
      top: 100%;
      left: 0;
      right: 0;
      background-color: #000;
      flex-direction: column;
      align-items: flex-start;
      border: none;
      border-radius: 0;
      padding: 1em 2em;
    }

    .logo img {
        height: 2em;
    }

    .navbar {

        padding-left: 2em;
        padding-right: 2em;
    }

    .menu-enter-active, .menu-leave-active {
      transition: transform 0.3s ease, opacity 0.3s ease;
    }
    .menu-enter-from, .menu-leave-to {
      transform: translateY(-40%);
      opacity: 0;
    }
    .menu-options ul {
      flex-direction: column;
      gap: 1em;
    }

    
  }
  </style>
  