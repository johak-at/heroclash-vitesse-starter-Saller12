<script setup>
import { useCardsStore } from '~/store/cards'
const cardsStore = useCardsStore()
const heroCards = ref([])
const hero = ref(null)
function switchHero(newHeroNumber) {
  if (Number.isInteger(newHeroNumber) && newHeroNumber > 0 && newHeroNumber < heroCards.value.length)
    hero.value = cardsStore.heroCards[newHeroNumber - 1].data
}

onMounted(async () => {
  await cardsStore.loadCards()
  hero.value = cardsStore.heroCards[0].data
})
</script>

<template>
  <HeroCard v-if="hero" :hero="hero" />
  <HeroSelector @changeHero="switchHero" />
</template>
