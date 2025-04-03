<script setup>
  defineProps(['string', 'active'])
  import AnimatedLetter from './AnimatedLetter.vue'
</script>

<template>
  <AnimatedLetter
      v-for="(letter, i) in string"
      :letter="letter"
      :active="active"
  />
</template>
