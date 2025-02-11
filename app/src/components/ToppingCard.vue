<template>
  <div class="Card">
    <img :src="topping.image" :alt="topping.name" class="topping-image" />
    <h3>{{ topping.name }}</h3>
  </div>
</template>

<script setup>
defineProps({
  topping: Object,
})
</script>

<style scoped>
.card {
  font-size: 20px;
}
</style>
