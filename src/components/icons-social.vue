<script setup></script>

<template>
  <div>
    <a href="#">
      <img src="../assets/icon-instagram.svg" alt="icon" />
    </a>
    <a href="#">
      <img src="../assets/icon-facebook.svg" alt="icon" />
    </a>
    <a href="#">
      <img src="../assets/icon-pinterest.svg" alt="icon" />
    </a>
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  height: 100%;
  width: 10%;
  margin: 0 auto;
}

img {
  transition: filter 0.3s;
}

a:hover img {
  filter: hue-rotate(345deg);
}
</style>
