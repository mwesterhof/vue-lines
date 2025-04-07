<script setup>
  import AnimatedString from './components/AnimatedString.vue'
  import { ref, computed } from 'vue'

  const marqueeText = ref('SOME MARQUEE TICKER TEXT')
  const newMarqueeText = ref('SOME MARQUEE TICKER TEXT')
  const marqueeLength = ref(5)
  const newMarqueeLength = ref(5)
  const active = ref(true)

  const marqueeSlice = computed(() => {
    return marqueeText.value.slice(0, marqueeLength.value)
  })

  setInterval(() => {
    marqueeText.value = marqueeText.value.slice(1) + marqueeText.value[0]
  }, 1500)
</script>

<template>
  <label>text</label>
  <input v-model="newMarqueeText" />
  <button @click="marqueeText=newMarqueeText">set</button>
  <br />
  <label>width</label>
  <input type="number" v-model="newMarqueeLength" />
  <button @click="marqueeLength=newMarqueeLength">set</button>
  <br />
  <button v-if="active" @click="active = false">deactivate</button>
  <button v-else @click="active = true">activate</button>
  <br />

  <AnimatedString @click="active = !active" :string="marqueeSlice" :active="active" />
</template>
