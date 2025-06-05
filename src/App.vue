<script setup>
import Navbar from "./components/Navbar.vue";
import Hero from "./components/Hero.vue";
import Firebrands from "./components/Firebrands.vue";

const leftFirebrands = [
  { velocity: 300, gravity: -200, left: 100, rotate: -90, delay: 0 },
  { velocity: 500, gravity: -600, left: 700, delay: 1 },
  { velocity: 100, gravity: -200, left: 50, rotate: -30, delay: 2 },
  { velocity: 600, gravity: -100, left: 100, delay: 3 },
  { velocity: 400, gravity: -120, left: 10, rotate: -100, delay: 1 },
  { velocity: 450, gravity: -300, left: 220, delay: 5 },
  { velocity: 110, gravity: -90, left: 33, rotate: -200, delay: 4 },
  { velocity: 20, gravity: -10, left: 25, delay: 7 },
  { velocity: 320, gravity: -190, left: 20, rotate: -250, delay: 3 },
];

const rightFirebrands = [
  { velocity: 300, gravity: -200, right: 100, rotate: -90, delay: 0 },
  { velocity: 500, gravity: -600, right: 700, delay: 1 },
  { velocity: 100, gravity: -200, right: 50, rotate: -30, delay: 2 },
  { velocity: 600, gravity: -100, right: 100, delay: 3 },
  { velocity: 400, gravity: -120, right: 10, rotate: -100, delay: 1 },
  { velocity: 450, gravity: -300, right: 220, delay: 5 },
  { velocity: 110, gravity: -90, right: 33, rotate: -200, delay: 4 },
  { velocity: 20, gravity: -10, right: 25, delay: 7 },
  { velocity: 320, gravity: -190, right: 20, rotate: -250, delay: 3 },
];
</script>

<template>
  <main class="container">
    <Navbar />
    <Hero />
    <Firebrands
      v-for="(brand, index) in leftFirebrands"
      :key="index"
      :velocity="brand.velocity"
      :gravity="brand.gravity"
      :left="brand.left"
      :rotate="brand.rotate"
      :delay="brand.delay"
    />
    <Firebrands
      v-for="(brand, index) in rightFirebrands"
      :key="index"
      :velocity="brand.velocity"
      :gravity="brand.gravity"
      :right="brand.right"
      :rotate="brand.rotate"
      :delay="brand.delay"
    />
  </main>
</template>

<style scoped>
.container {
  margin: 30px;
  padding: 30px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background: linear-gradient(
    150deg,
    var(--bgColor-rbga-primary) 8%,
    var(--bgColor-rbga-secondary) 100%
  );
}
</style>
