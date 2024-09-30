<template>
  <div class="header-content">
    <p class="title">
      <span class="part2">Government </span>
      <span class="part1">on Demand</span>
    </p>
    <p class="subtitle">
      Somos tu brújula en el panorama político, analizando las acciones y decisiones de los poderes públicos
      <!---<span class="flip" ref="flipAnimation"></span>-->
    </p>
  </div>
</template>

<script setup>
import { ref, onMounted, nextTick } from 'vue';

const flipAnimation = ref(null);
const frames = [
  "⠁", "⠂", "⠄", "⡀", "⡈", "⡐", "⡠", "⣀", "⣁", "⣂",
  "⣄", "⣌", "⣔", "⣤", "⣥", "⣦", "⣮", "⣶", "⣷", "⣿",
  "⡿", "⠿", "⢟", "⠟", "⡛", "⠛", "⠫", "⢋", "⠋", "⠍",
  "⡉", "⠉", "⠑", "⠡", "⢁"
];

let frameIndex = 0;

const animateFlip = () => {
  if (flipAnimation.value) {
    flipAnimation.value.textContent = frames[frameIndex];
    frameIndex = (frameIndex + 1) % frames.length;
  }
};

onMounted(() => {
  nextTick(() => {
    setInterval(animateFlip, 100); // Adjust the interval time as needed
  });
});
</script>


<style scoped>
.header-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  padding: 20px;
  padding-left: 3.5em;
  height: 50vh;
  max-width: 80vh;
  color: #253743;
}

h1, h2 {
  margin: 0;
}

.subtitle {
  font-size: 1.2em;
  font-weight: 400;
}

.title {
  font-size: 2.2em;
  margin: 0;
}

.part1 {
  font-weight: 400;
  font-family: 'Space Grotesk', sans-serif;
}

.part2 {
  font-weight: 700;
  font-family: 'Space Grotesk', sans-serif;
}

.flip {
  display: inline-block;
  font-family: monospace;
  margin-left: 5px;
  font-weight: 200;
}

@media (max-width: 768px) {
  .header-content {
    padding-left: 2em;
  }
}
</style>
