<script setup>
  import AnimatedString from './components/AnimatedString.vue'
  import { ref } from 'vue'

  const lettersActive = ref(true);
  const value = ref('DEADBEEF')

  setInterval(() => {
    //lettersActive.value = !lettersActive.value
  }, 2000)
</script>

<template>
  <p>home: {{ value }}</p>
  <input v-model="value" />
  <button @click="lettersActive = false" v-if="lettersActive">deactivate</button>
  <button @click="lettersActive = true" v-else>activate</button>
  <br />
  <AnimatedString :string="value" :active="lettersActive" />
</template>
