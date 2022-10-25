<script setup>
const props = defineProps(['hero'])
</script>

<template>
  <div grid class="card">
    <HeroImage :image-url="hero.images.md" />
    <HeroStats :name="hero.name" :stats="hero.powerstats" :alignment="hero.biography.alignment" />
  </div>
</template>

<style scoped>
    .card{
        width: 330px;
        height:230px;
        grid-template-columns: 1fr 1.2fr;
    }
</style>
