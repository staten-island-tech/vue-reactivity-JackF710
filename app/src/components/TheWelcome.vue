<script setup>
import ToppingsList from '@/components/ToppingsList.vue'
import ToppingCard from '@/components/ToppingCard.vue'
import breads from '@/components/ToppingsList.vue'


</script>

<template>
  <div class="Card">
    <img :src="topping.image" :alt="topping.name" class="topping-image" />
    <h3>{{ topping.name }}</h3>
  </div>
</template>
