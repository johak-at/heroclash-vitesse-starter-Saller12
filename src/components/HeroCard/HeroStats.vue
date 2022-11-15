<script setup>
const props = defineProps(['name', 'stats', 'alignment'])
</script>

<template>
  <div :class="alignment">
    <h1>{{ name }}</h1>
    <StatField v-for="(value, key) in stats" :key="key" :skill="key" :value="value">
      {{ key }} : {{ value }}
    </StatField>
  </div>
</template>

<style scoped>
.bad
{
    background-image: linear-gradient(to right, #f12711, #f5af19);
}

.good
{
    background-image: linear-gradient(135deg, #00b09b, #96c93d);
}

.neutral
{
    background-image: linear-gradient(135deg, #f5af19, #96c93d);
}
</style>

