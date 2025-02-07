<template>
  <BreadCard v-for="bread in breads" :key="bread.name" :bread="bread" />
  <MeatCard v-for="meat in meats" :key="name" :meat="meat" />
  <CheeseCard v-for="cheese in cheeses" :key="name" :cheese="cheese" />
  <CondimentCard v-for="condiment in condiments" :key="name" :condiment="condiment" />
  <VegetableCard v-for="vegetable in vegetables" :key="name" :vegetable="vegetable" />
  <h1>{{ bread.name }}</h1>
  <h1>{{ meat.name }}</h1>
  <h1>{{ cheese.name }}</h1>
  <h1>{{ condiment.name }}</h1>
  <h1>{{ vegetable.name }}</h1>
</template>

<script setup>
import './components/ToppingsList.vue'
import bread from './components/ToppingsList.vue'
import meat from './components/ToppingsList.vue'
import cheese from './components/ToppingsList.vue'
import condiment from './components/ToppingsList.vue'
import vegetable from './components/ToppingsList.vue'
</script>

<style scoped></style>
