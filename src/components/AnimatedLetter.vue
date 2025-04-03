<script setup>
  import { ref, computed } from 'vue'
  import '../assets/letters.css'

  const active = ref(true)
  const letters = ref(['A', 'B', 'C', 'D', 'E']);
  const index = ref(0)
  const letterClass = computed(() => {
    return letters.value[index.value]
  })

  setInterval(() => {
    index.value += 1
    if (index.value >= 5) {
      index.value -= 5;
    }
  }, 1000)
</script>

<template>
  <p>{{ letterClass }}</p>
  <div @click="active = !active" class="letter active" :class="letterClass">
    <div class="line line1"></div>
    <div class="line line2"></div>
    <div class="line line3"></div>
    <div class="line line4"></div>
    <div class="line line5"></div>
    <div class="line line6"></div>
    <div class="line line7"></div>
    <div class="line line8"></div>
    <div class="line line9"></div>
    <div class="line line10"></div>
  </div>
</template>

<style scoped>
  .letter {
    --size: 10rem;
    --color: #FFFFFF;
    --color-inactive: #FFFFFF08;
    --color-background: #8888FF;
    --time: .5s;
  }

  .letter {
    background-color: var(--color-background);
    width: var(--size);
    height: var(--size);
    position: relative;
  }

  .letter .line {
    background-color: var(--color);
    width: var(--size);
    height: calc(var(--size) / 15);
    position: absolute;
    top: 0;
    left: 0;
    rotate: 0deg;
    transition: all var(--time);
    border-radius: calc(var(--size) / 10);
  }

  /*
  .letter.A.active .line1,
  .letter.A.active .line2,
  .letter.A.active .line3,
  .letter.A.active .line4,
  .letter.A.active .line5,
  .letter.A.active .line6,
  .letter.A.active .line7,
  .letter.A.active .line8,
  .letter.A.active .line9,
  .letter.A.active .line10 {
    top: calc(var(--size) * 0.9375);
    background-color: var(--color-inactive);
  }
  */
</style>
