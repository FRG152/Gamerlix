<script setup></script>

<template>
  <div class="container">
    <div class="box-danger">
      <div class="line-top-left"></div>
      <div class="line-top-right"></div>
      <h1>DANGER</h1>
      <div class="line-bottom-left"></div>
      <div class="line-bottom-right"></div>
    </div>
    <div class="box-line">
      <div class="line"></div>
      <div class="line"></div>
      <div class="line"></div>
      <div class="line"></div>
      <div class="line"></div>
      <div class="line"></div>
      <div class="line"></div>
    </div>
  </div>
</template>

<style scoped>
.container {
  width: 30%;
  height: 100%;
  padding: 30px;
  display: flex;
  position: relative;
  flex-direction: column;
  gap: 20px;
}
.container::before {
  content: "";
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
  filter: blur(30px);
  position: absolute;
  clip-path: polygon(0 0, 90% 0, 100% 0%, 100% 100%, 0 100%, 0% 100%);
  background-color: rgba(0, 0, 0, 0.8);
  z-index: 0;
}
.box-danger {
  height: 100%;
  padding: 1px;
  display: flex;
  position: relative;
  align-items: center;
  justify-content: center;
}
.box-danger > h1 {
  color: var(--color-primary);
  font-size: 2rem;
}
.line-top-left {
  top: 0;
  left: 0;
  width: 15px;
  height: 15px;
  position: absolute;
  background-color: var(--color-primary);
  clip-path: polygon(
    0 0,
    100% 0,
    100% 25%,
    25% 25%,
    25% 100%,
    0 100%,
    0 65%,
    0 35%
  );
}
.line-top-right {
  top: 0;
  right: 0;
  width: 15px;
  height: 15px;
  transform: rotate(90deg);
  position: absolute;
  background-color: var(--color-primary);
  clip-path: polygon(
    0 0,
    100% 0,
    100% 25%,
    25% 25%,
    25% 100%,
    0 100%,
    0 65%,
    0 35%
  );
}
.line-bottom-left {
  left: 0;
  bottom: 0;
  width: 15px;
  height: 15px;
  transform: rotate(270deg);
  position: absolute;
  background-color: var(--color-primary);
  clip-path: polygon(
    0 0,
    100% 0,
    100% 25%,
    25% 25%,
    25% 100%,
    0 100%,
    0 65%,
    0 35%
  );
}
.line-bottom-right {
  right: 0;
  bottom: 0;
  width: 15px;
  height: 15px;
  transform: rotate(180deg);
  position: absolute;
  background-color: var(--color-primary);
  clip-path: polygon(
    0 0,
    100% 0,
    100% 25%,
    25% 25%,
    25% 100%,
    0 100%,
    0 65%,
    0 35%
  );
}
.box-line {
  width: 100%;
  height: 100%;
  display: flex;
  position: relative;
  flex-direction: row;
}
.line {
  width: 100%;
  height: 100%;
  clip-path: polygon(25% 0, 100% 0%, 75% 100%, 0% 100%);
  background-color: var(--color-primary);
}
</style>
