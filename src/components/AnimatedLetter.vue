<script setup>
  defineProps(['letter', 'active'])
  import '../assets/letters.css'
</script>

<template>
  <div class="letter" :class="[letter, {active: active}]">
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
    --size: 2rem;
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
    float: left;
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
