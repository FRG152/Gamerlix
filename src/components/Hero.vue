<script setup>
import gsap from "gsap";
import Danger from "./Danger.vue";
import CardComponent from "./CardComponent.vue";
import { ref, onMounted } from "vue";

const boxCard = ref(null);
const image = ref(null);
const title = ref(null);

onMounted(() => {
  gsap.from(title.value, {
    opacity: 0,
    duration: 2,
    x: -300,
    ease: "power2.inOut",
  });
  gsap.from(boxCard.value, {
    opacity: 0,
    duration: 4,
    y: -100,
    ease: "power2.inOut",
  });
  gsap.from(image.value, {
    opacity: 0,
    duration: 4,
    y: 100,
    ease: "power2.inOut",
  });
});
</script>

<template>
  <section ref="containerHero" class="container-hero">
    <h1 ref="title" class="hero-title">NEXSUS</h1>
    <img ref="image" alt="hero" class="image" src="../../public/image01.png" />
    <div ref="boxCard" class="box-card">
      <CardComponent
        title="BEST GAMES"
        desc="Inmerse in the ultimate rush! The pinnacle of futuristic racing games - the epitome of speed and thrill. Experience the best games ever!"
      />
      <CardComponent
        title="NEW LOCATION"
        desc="The new update features exciting locations such as neon-lit cityscapes, zero-gravity tunnels and space tracks with asteroids and obstacles!"
      />
      <!-- <CardComponent
        title="NEW CHARACTERS"
        desc="Added new characters such as cyborg racers, racers with enhanced artificial intelligence and alien speedsters with unique abilities!"
      /> -->
      <Danger />
    </div>
  </section>
</template>

<style scoped>
@import "../assets/base.css";

.container-hero {
  display: flex;
  min-height: calc(100vh - 180px);
  align-items: center;
  justify-content: center;
}
.hero-title {
  color: var(--color-primary);
  margin: 0;
  font-size: 18rem;
  text-align: center;
  text-shadow: 10px 10px 3px var(--shadow-primary);
}
.image {
  left: 0;
  right: 0;
  bottom: 0;
  height: 800px;
  margin: auto;
  position: absolute;
  object-fit: contain;
  filter: drop-shadow(30px 10px 4px var(--shadow-primary));
}
.box-card {
  left: 0;
  right: 0;
  bottom: 80px;
  display: flex;
  position: absolute;
  align-items: center;
  margin: auto;
  height: 120px;
  width: calc(100% - 110px);
  gap: 10px;
}
@media screen and (max-width: 1000px) {
  .hero-title {
    font-size: 8rem;
  }
  .image {
    height: 500px;
  }
  .box-card {
    display: flex;
    flex-direction: column;
  }
}
@media screen and (max-width: 1000px) {
  .hero-title {
    font-size: 8rem;
  }
  .image {
    height: 500px;
  }
  .box-card {
    display: flex;
    flex-direction: column;
  }
}
</style>
