<script setup>
import Timer from '@/components/Timer.vue'
</script>

<template>
  <div class="main-con">
    <h1>Timer</h1>
    <div class="timer-con">
      <Timer />
    </div>
  </div>
</template>
<style scoped lang="scss">
.main-con {
  display: flex;
  flex-direction: column;
  align-items: center;

  h1 {
    text-align: center;
    font-family: 'Baloo 2', sans-serif;
    font-optical-sizing: auto;
    font-weight: 800;
    font-style: normal;
    font-size: 3rem;
    background: #30cfb7;
    border-radius: 50px;
    padding: 0.8rem 5rem;
    margin: 1rem;
  }

  .timer-con {
    display: flex;
    justify-content: center;
    align-items: center;
  }
}
</style>
