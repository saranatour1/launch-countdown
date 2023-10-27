<script setup>
import CountDown from './components/count-down.vue';
import IconsSocial from './components/icons-social.vue';
import LaunchText from './components/launch-text.vue';
</script>

<template>
  <main>
    <LaunchText />
    <CountDown />
  </main>
  <footer>
    <IconsSocial/>
  </footer>
</template>

<style scoped>
  *{
    padding: 0;
    margin: 0;
  }
  
</style>
