<script setup>
const props = defineProps(['name', 'appearance', 'biography', 'connections', 'work'])
const emits = defineEmits(['hideBiography'])
</script>

<template>
  <div class="modal" @click="emits('hideBiography')">
    <h1>{{ name }}</h1>
    <div class="modal-content">
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
  </div>
</template>

<style scoped>
.modal-content {
  color: black;
  background-color: lightblue;
  margin: 15% auto; /* 15% from the top and centered */
  padding: 20px;
  border: 1px solid #888;
  width: 80%; /* Could be more or less, depending on screen size */
}

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
.h1{
  text-align: center;
  background-image: linear-gradient(135deg, #00b09b, #96c93d);
}
</style>
