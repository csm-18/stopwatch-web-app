<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
let hours = ref(0)
let minutes = ref(0)
let seconds = ref(0)
let max_time = ref('0:0')

let timer_on = ref(true)
let intervalId = null

function updateTime() {
  if (seconds.value == 60) {
    if (minutes.value == 60) {
      hours.value += 1
      minutes.value = 0
    } else {
      minutes.value += 1
      seconds.value = 0
    }
  } else {
    seconds.value += 1
  }
}

function startStop() {
  if (timer_on.value) {
    timer_on.value = false
    intervalId = setInterval(updateTime, 1000)
  } else {
    timer_on.value = true
    clearInterval(intervalId)
  }
}

function resetValues() {
  timer_on.value = true
  clearInterval(intervalId)
  hours.value = 0
  minutes.value = 0
  seconds.value = 0
}

onUnmounted(() => {
  clearInterval(intervalId)
})
</script>

<template>
  <div class="main-con">
    <div class="values" @click="resetValues">
      <p>{{ hours }}</p>
      <p>:</p>
      <p>{{ minutes }}</p>
      <p>:</p>
      <p>{{ seconds }}</p>
    </div>
    <button class="start-stop-btn" @click="startStop">Start/Stop</button>
  </div>
</template>

<style scoped lang="scss">
.main-con {
  padding: 5rem;

  .values {
    display: flex;
    flex-direction: row;
    gap: 0.5rem;
    font-size: 5rem;
    padding-bottom: 2rem;
  }

  .start-stop-btn {
    border: 0;
    background: rgb(249, 149, 149);
    font-size: 2rem;
    padding: 1rem;
    border-radius: 50px;
  }
}
</style>
