<script setup>
const props = defineProps(['name', 'appearance', 'biography', 'connections', 'work'])
const emits = defineEmits(['hideBiography'])
</script>

<template>
  <div class="modal" @click="emits('hideBiography')">
    <ul>
      <li v-for="(value, key) in biography" :key="key">
        <p>{{ key }}: {{ value }}</p>
      </li><li v-for="(value, key) in appearance" :key="key">
        <p>{{ key }}: {{ value }}</p>
      </li><li v-for="(value, key) in work" :key="key">
        <p>{{ key }}: {{ value }}</p>
      </li><li v-for="(value, key) in connections" :key="key">
        <p>{{ key }}: {{ value }}</p>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.modal
{
  position: fixed;
    top: 0;
    left: 0;
    z-index: 1;
    width: 100vw;
    height: 100vh;
    position: fixed;
    background-color: rgba(0, 221, 255, 0.4);

}
.modal-overlay
{
  /*Style vorher*/
  /*position: fixed;
    top: 0;
    left: 0;
    z-index: 1;
    width: 100vw;
    height: 100vh;
    position: fixed;*/
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 1;
  display: flex;
  justify-content: center;
  background-color: rgba(0, 221, 255, 0.4);
}
</style>
