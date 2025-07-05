<script setup>
import Stopwatch from '@/components/Stopwatch.vue'
</script>

<template>
  <div class="main-con">
    <h1>Stopwatch</h1>
    <div class="stopwatch-con">
      <Stopwatch />
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

  .stopwatch-con {
    display: flex;
    justify-content: center;
    align-items: center;
  }
}
</style>
