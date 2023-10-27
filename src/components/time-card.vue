<script setup>
defineProps({
  title: String,
  time: Number
})
</script>

<template>
  <div>
    <div class="inner">
      <p v-if="time < 10">0{{ time }}</p>
      <p v-else>{{ time }}</p>
    </div>

    <h2>{{ title }}</h2>
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 10rem;
  height: 10rem;
}

.inner {
  background-color: var(--dark-desaturated-blue);
  border-radius: 1rem;
  box-shadow: rgba(0, 0, 0, 0.4) 0px 2px 4px, rgba(0, 0, 0, 0.3) 0px 7px 13px -3px, rgba(0, 0, 0, 0.2) 0px -3px 0px inset;
}

.inner::before{
  width: 4rem;
  height: 4rem;
  background-color: aqua;
}


div > p {
  color: var(--soft-red);
  font-size: 4rem;
}

h2 {
  font-size: 0.8rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
  color: var(--grayish-blue);
  letter-spacing: 0.3rem;
  text-transform: uppercase;
  text-align: center;
}


</style>
