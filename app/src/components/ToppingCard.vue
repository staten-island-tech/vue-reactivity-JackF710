<template>
      <div class="card">
                <img :src="vegetable.image" alt="vegetable.name" />
                <h3>{{ vegetable.name }}</h3>
                <p>${{ vegetable.price }}</p>
              </div>
    <div class="card">
                <img :src="condiment.image" alt="condiment.name" />
                <h3>{{ condiment.name }}</h3>
                <p>${{ condiment.price }}</p>
              </div>
              <div class="card">
                <img :src="cheese.image" alt="cheese.name" />
                <h3>{{ cheese.name }}</h3>
                <p>${{ cheese.price }}</p>
              </div>
              <div class="card">
                <img :src="meat.image" alt="meat.name" />
                <h3>{{ meat.name }}</h3>
                <p>${{ meat.price }}</p>
              </div>
              <div class="card">
                <img :src="bread.image" alt="bread.name" />
                <h3>{{ bread.name }}</h3>
                <p>${{ bread.price }}</p>
              </div>
  </template>
  
  <script setup>
  defineProps({
    topping: Object,
  });
  </script>
  
  <style scoped>
  .topping-card {
    border: 1px solid #ddd;
    border-radius: 10px;
    padding: 10px;
    text-align: center;
    width: 180px;
    box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
    background: white;
  }
  
  .topping-image {
    width: 100px;
    height: 100px;
    object-fit: cover;
    border-radius: 50%;
  }
  </style>
  