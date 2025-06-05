<script setup>
import Hero from "./components/Hero.vue";
import Navbar from "./components/Navbar.vue";
import Firebrands from "./components/Firebrands.vue";
import { ref, onMounted } from "vue";
import { leftFirebrands, rightFirebrands } from "./constants";

const container = ref(null);
const cursor = ref(null);

onMounted(() => {
  const heading = document.querySelector(".hero-title");

  window.addEventListener("mousemove", (e) => {
    cursor.value.style.left = `${e.clientX}px`;
    cursor.value.style.top = `${e.clientY}px`;
  });

  heading.addEventListener("mouseenter", () => {
    cursor.value.style.width = "150px";
    cursor.value.style.height = "150px";
    cursor.value.style.backgroundColor = "#000";
  });

  heading.addEventListener("mouseleave", () => {
    cursor.value.style.width = "100px";
    cursor.value.style.height = "100px";
    cursor.value.style.backgroundColor = "#fff";
  });
});
</script>

<template>
  <main ref="container" class="container">
    <div ref="cursor" class="custom-cursor"></div>
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
  overflow: hidden;
}
.custom-cursor {
  position: fixed;
  top: 0;
  left: 0;
  width: 100px;
  height: 100px;
  transform: translate(-50%, -50%);
  transition: all 0.1s;
  border-radius: 50%;
  pointer-events: none;
  background-color: var(--color-primary);
}
</style>
