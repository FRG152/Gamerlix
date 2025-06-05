<script setup>
import { defineProps } from "vue";

const props = defineProps({
  title: String,
  desc: String,
});
</script>

<template>
  <div class="container-card">
    <h1 class="card-title">{{ title }}</h1>
    <p class="card-desc">{{ desc }}</p>
  </div>
</template>

<style scoped>
.container-card {
  height: 100%;
  padding: 30px;
  display: flex;
  position: relative;
  font-family: "Poppins", sans-serif;
  align-items: flex-start;
  flex-direction: column;
  justify-content: center;
  gap: 20px;
}
.container-card::before {
  content: "";
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
  filter: blur(30px);
  position: absolute;
  clip-path: polygon(0 0, 90% 0, 100% 26%, 100% 100%, 0 100%, 0% 50%);
  background-color: rgba(0, 0, 0, 0.8);
  z-index: 0;
}
.container-card::after {
  content: "";
  top: 0;
  right: 0;
  width: 9%;
  height: 22.5%;
  position: absolute;
  clip-path: polygon(0 1%, 100% 0, 100% 50%, 100% 100%, 100% 100%, 0% 0%);
  background-color: var(--color-primary);
  z-index: 0;
}
.card-title {
  color: var(--color-primary);
  z-index: 100 !important;
  position: sticky;
  font-size: 2rem;
}
.card-desc {
  color: var(--color-primary);
  z-index: 100;
  position: sticky;
  font-size: 0.9rem;
  font-weight: 100 !important;
}
</style>
