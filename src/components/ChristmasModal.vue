<template>
  <Transition name="modal">
    <div v-if="isVisible" class="modal-overlay" @click.self="closeModal">
      <div class="modal-content">
        <button class="close-btn" @click="closeModal" aria-label="Cerrar">
          &times;
        </button>
        <img
          src="/unnamed.jpg"
          alt="Feliz Navidad y Próspero Año 2026"
          class="greeting-image"
        />
      </div>
    </div>
  </Transition>
</template>

<script setup>
import { ref } from 'vue';

const hasSeenModal = sessionStorage.getItem('christmasModalSeen');
const isVisible = ref(!hasSeenModal);

const closeModal = () => {
  isVisible.value = false;
  sessionStorage.setItem('christmasModalSeen', 'true');
};
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
  padding: 1rem;
  box-sizing: border-box;
}

.modal-content {
  position: relative;
  max-width: 90vw;
  max-height: 90vh;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
}

.greeting-image {
  display: block;
  width: 100%;
  height: auto;
  max-width: 500px;
  max-height: 85vh;
  object-fit: contain;
}

.close-btn {
  position: absolute;
  top: 10px;
  right: 10px;
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: none;
  background-color: rgba(255, 255, 255, 0.9);
  color: #333;
  font-size: 24px;
  line-height: 1;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.2s ease;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
}

.close-btn:hover {
  background-color: #fff;
  transform: scale(1.1);
}

/* Transition animations */
.modal-enter-active,
.modal-leave-active {
  transition: opacity 0.3s ease;
}

.modal-enter-active .modal-content,
.modal-leave-active .modal-content {
  transition: transform 0.3s ease;
}

.modal-enter-from,
.modal-leave-to {
  opacity: 0;
}

.modal-enter-from .modal-content,
.modal-leave-to .modal-content {
  transform: scale(0.9);
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .modal-content {
    max-width: 95vw;
  }

  .greeting-image {
    max-width: 100%;
  }

  .close-btn {
    top: 8px;
    right: 8px;
    width: 32px;
    height: 32px;
    font-size: 20px;
  }
}

@media (max-width: 480px) {
  .modal-overlay {
    padding: 0.5rem;
  }

  .modal-content {
    border-radius: 8px;
  }

  .close-btn {
    top: 6px;
    right: 6px;
    width: 28px;
    height: 28px;
    font-size: 18px;
  }
}
</style>
