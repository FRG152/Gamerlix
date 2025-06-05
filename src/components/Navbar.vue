<script setup>
import gsap from "gsap";
import { ref, onMounted } from "vue";

const navbar = ref(null);

onMounted(() => {
  gsap.from(navbar.value, {
    opacity: 0,
    duration: 2,
    y: -100,
    ease: "power2.inOut",
  });
});
</script>

<template>
  <nav ref="navbar" class="navbar">
    <ul class="nav-links">
      <div class="nav-logo">
        <h3>GAMERLIX</h3>
      </div>
      <li class="nav-link">NEWS</li>
      <li class="nav-link">FORUM</li>
      <li class="nav-link">ABOUT US</li>
      <li class="nav-link">OTHER GAMES</li>
      <li class="nav-link">NEWS</li>
      <button class="nav-join">JOIN TO BETA</button>
    </ul>
  </nav>
</template>

<style scoped>
.navbar {
  height: 60px;
  font-family: "Poppins", sans-serif;
}
.nav-links {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.nav-logo > h3 {
  font-size: 2.2rem;
  color: var(--color-primary);
}
.nav-link {
  color: var(--color-primary);
  cursor: pointer;
  transition: all 0.2s;
  font-weight: 100;
}
.nav-link:hover {
  letter-spacing: 0.3rem;
}
.nav-join {
  color: var(--color-primary);
  padding: 20px;
  clip-path: polygon(15% 0%, 100% 0, 100% 50%, 100% 100%, 0 100%, 0 35%);
  transition: all 0.2s;
  font-weight: 600;
  font-family: "Poppins", sans-serif;
  border-right: 5px solid var(--color-primary);
  background-color: rgba(0, 0, 0, 0.25);
}
.nav-join:hover {
  color: var(--color-secondary);
  border-right: 5px solid var(--color-secondary);
  background-color: var(--color-primary);
}
@media screen and (max-width: 768px) {
  .nav-logo > h3 {
    font-size: 1rem;
  }
  .nav-link {
    display: none;
  }
  .nav-join {
    display: none;
  }
}
</style>
