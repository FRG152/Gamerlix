<script setup>
import Navbar from "./components/Navbar.vue";
import Hero from "./components/Hero.vue";
import Firebrands from "./components/Firebrands.vue";
import { leftFirebrands, rightFirebrands } from "./constants";
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
