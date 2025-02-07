<template>
  <div>
    <h2 v-for="bread in breads" :key="name">{{ bread }}</h2>
    <h2 v-for="meat in meats" :key="name">{{ meat }}</h2>
    <h2 v-for="cheese in cheeses" :key="name">{{ cheese }}</h2>
    <h2 v-for="condiment in condiments" :key="name">{{ condiment }}</h2>
    <h2 v-for="vegetable in vegetables" :key="name">{{ vegetable }}</h2>
  </div>
</template>

<script setup>
defineProps({
  bread: Object,
  meat: Object,
  cheese: Object,
  condiment: Object,
  vegetable: Object,
})
</script>

<style scoped></style>
