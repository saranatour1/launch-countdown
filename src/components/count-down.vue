<script setup>
import { ref, onMounted } from 'vue'
import TimeCard from './time-card.vue'

const timeUntil = new Date('2025-01-01 00:00:00')
const timeObject = ref(calculateCountdown())

function calculateCountdown() {
  const timeNow = new Date()
  const timeDifference = timeUntil - timeNow

  if (timeDifference <= 0) {
    // Countdown has ended
    return { days: 0, hours: 0, minutes: 0, seconds: 0 }
  }

  const oneSecond = 1000
  const oneMinute = oneSecond * 60
  const oneHour = oneMinute * 60
  const oneDay = oneHour * 24

  const days = Math.floor(timeDifference / oneDay)
  const hours = Math.floor((timeDifference % oneDay) / oneHour)
  const minutes = Math.floor((timeDifference % oneHour) / oneMinute)
  const seconds = Math.floor((timeDifference % oneMinute) / oneSecond)

  return { days, hours, minutes, seconds }
}

function updateCountdown() {
  timeObject.value = calculateCountdown()
}

onMounted(() => {
  const timeID = setInterval(updateCountdown, 1000)
  return () => clearInterval(timeID)
})
</script>

<template>
  <div>
    <TimeCard v-for="(value, key) in timeObject" :key="key" :title="key" :time="value" />
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
  justify-content: space-evenly;
  width: 90%;
  margin: 3rem auto;
  user-select: none;
  gap: 14px;
}
</style>
