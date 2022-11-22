<script setup>
const emits = defineEmits(['changeHero'])
const heroNumber = ref(1)
</script>

<template>
  <label for="heroNumber"> Choose Hero</label>
  <input id="heroNumber" v-model="heroNumber" type="number" min="1" @input="emits('changeHero', heroNumber)">
</template>
