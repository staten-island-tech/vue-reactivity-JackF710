<template>
  <div>
    <h1>Build a Subway Sandwich</h1>
    <ToppingsList />
  </div>
</template>

<script setup>
import ToppingsList from '@/components/ToppingsList.vue';
</script>

<style scoped>
h1 {
  text-align: center;
  font-size: 3rem;
  font-weight: bold;
  margin: 20px;
  margin-right: -100%;
  color: #333;
  letter-spacing: 2px;
  text-transform: uppercase;
  font-family: 'Arial', sans-serif;
}

h1::after {
  content: "";
  display: block;
  width: 50%;
  height: 2px;
  background-color: #fbbc11;
  margin: 10px auto;
}

</style>