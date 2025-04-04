<script setup>
  import AnimatedString from './components/AnimatedString.vue'
  import { ref } from 'vue'

  const lettersActive = ref(true);
  const value = ref('ABCDEFGHIJKLM  ')

  setInterval(() => {
    //lettersActive.value = !lettersActive.value
    value.value = value.value.slice(1) + value.value[0]
  }, 1000)
</script>

<template>
  <button @click="lettersActive = false" v-if="lettersActive">deactivate</button>
  <button @click="lettersActive = true" v-else>activate</button>
  <br />
  <br />
  <br />
  <AnimatedString :string="value" :active="lettersActive" />
</template>
