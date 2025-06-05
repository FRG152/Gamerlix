<script setup>
import gsap from "gsap";
import { Physics2DPlugin } from "gsap/all";
import { onMounted, defineProps, ref } from "vue";

const props = defineProps({
  duration: Number,
  velocity: Number,
  gravity: Number,
  rotate: Number,
  delay: Number,
  right: Number,
  left: Number,
});

gsap.registerPlugin(Physics2DPlugin);

const velocity = props.velocity ?? gsap.utils.random(200, 500);
const gravity = props.gravity ?? gsap.utils.random(100, 200);
const rotate = props.rotate ?? 0;
const delay = props.delay ?? Math.floor(Math.random() * 5);
const right = props.right ?? Math.floor(Math.random() * 500);
const left = props.left ?? Math.floor(Math.random() * 500);

const cube01 = ref(null);
const cube02 = ref(null);

onMounted(() => {
  gsap.fromTo(
    cube01.value,
    {
      delay,
      repeat: -1,
      physics2D: {
        velocity,
        gravity,
      },
      ease: "sine.out",
    },
    {
      delay,
      repeat: -1,
      duration: 5,
      physics2D: {
        velocity,
        gravity,
        rotate,
      },
      ease: "sine.out",
    }
  );
  gsap.fromTo(
    cube02.value,
    {
      delay,
      repeat: -1,
      physics2D: {
        velocity,
        gravity,
      },
      ease: "sine.out",
    },
    {
      delay,
      repeat: -1,
      duration: 5,
      physics2D: {
        velocity,
        gravity,
        rotate,
      },
      ease: "sine.out",
    }
  );
});
</script>

<template>
  <div ref="cube01" class="cube01" :style="{ left: left + 'px' }" />
  <div ref="cube02" class="cube02" :style="{ right: right + 'px' }" />
</template>

<style scoped>
.cube01 {
  width: 5px;
  height: 5px;
  box-shadow: 2px 1px 6px yellow;
  border-radius: 100%;
  background-color: orange;
  position: absolute;
  bottom: -10px;
}
.cube02 {
  width: 5px;
  height: 5px;
  box-shadow: 2px 1px 6px yellow;
  border-radius: 100%;
  background-color: orange;
  position: absolute;
  bottom: -10px;
}
</style>
