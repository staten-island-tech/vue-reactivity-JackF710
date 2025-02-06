<template>
  <div>
    <h2>{{ bread.name }}</h2>
  </div>
</template>

<script setup>
import ToppingsList from './ToppingsList.vue'
defineProps({
  bread: Object,
  meat: Object,
  cheese: Object,
  condiment: Object,
  vegetable: Object,
})
</script>

<style scoped></style>
