<template>
  <div>
    <h2 v-for="bread in breads" :key="bread">{{ bread }}</h2>
  </div>
</template>

<script setup>
const breads = [
  'Wheat Bread',
  'White Bread',
  'Italian Herb & Cheese',
  'Malted Rye',
  'Plain Wrap',
  'Gluten Free Wrap',
  'Multigrain Wrap',
]
</script>

<style scoped></style>
