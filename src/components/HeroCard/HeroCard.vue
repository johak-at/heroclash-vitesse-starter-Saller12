<script setup>
const props = defineProps(['hero'])
const showBiography = ref(false)
</script>

<template>
  <HeroModal
    v-if="showBiography" @hideBiography="showBiography = false"
  />
  <div grid class="card">
    <HeroImage
      :image-url="hero.images.md"
      @showBiography="showBiography = true"
    />
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
