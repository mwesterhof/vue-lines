<script setup>
  import AnimatedLetter from './components/AnimatedLetter.vue'
  import { ref } from 'vue'

  const lettersActive = ref(true);
  setInterval(() => {
    lettersActive.value = !lettersActive.value
  }, 2000)
</script>

<template>
  <p>home</p>
  <AnimatedLetter letter="A" :active="lettersActive" />
  <AnimatedLetter letter="B" :active="lettersActive" />
  <AnimatedLetter letter="C" :active="lettersActive" />
</template>
