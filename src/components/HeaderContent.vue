<template>
  <div class="header-content">
    <p class="title">
      <span class="part1">Specialized Reasoning</span>, 
      <span class="part2">at scale</span>.
    </p>
    <p class="subtitle">
      Systems capable of solving problems and executing tasks in law, tax, and judicial matters
      <span class="flip" ref="flipAnimation"></span>
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
  color: aliceblue;
}

h1, h2 {
  margin: 0;
}

.subtitle {
  font-size: 1.4em;
  font-weight: 200;
}

.title {
  font-size: 2.2em;
  margin: 0;
}

.part1 {
  font-weight: 400;
}

.part2 {
  font-weight: 700;
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
