<script setup>
import BreadList from '../components/BreadList.vue'
defineProps({
  bread: Object,
})
</script>

<template>
  <main>
    <h1>Choose a Bread</h1>
    <h3>{{ breads }}</h3>
  </main>
</template>
