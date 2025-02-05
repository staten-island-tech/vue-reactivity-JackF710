<template>
  <div>
    <h2 v-for="bread in breads" :key="bread">{{ bread }}</h2>
    <h2 v-for="meat in meats" :key="meat">{{ meat }}</h2>
    <h2 v-for="cheese in cheeses" :key="cheese">{{ cheese }}</h2>
    <h2 v-for="condiment in condiments" :key="condiment">{{ condiment }}</h2>
    <h2 v-for="vegetable in vegetables" :key="vegatable">{{ vegetable }}</h2>
  </div>
</template>

<script setup>
const breads = [
  { name: 'Wheat Bread' },
  { name: 'White Bread' },
  { name: 'Italian Bread' },
  { name: 'Malted Rye' },
  { name: 'Plain Wrap' },
  { name: 'Gluten Free Wrap' },
  { name: 'Multigrain Wrap' },
]
const meats = [
  { name: 'Oven Roasted Chicken' },
  { name: 'Sweet Onion Chicken Teriyaki' },
  { name: 'Grilled Chicken' },
  { name: 'Meatballs' },
  { name: 'Roast Beef' },
  { name: 'Turkey Breast' },
  { name: 'Turkey Bacon' },
  { name: 'Salami' },
  { name: 'Pepperoni' },
  { name: 'Bacon' },
  { name: 'Black Forest Ham' },
  { name: 'Tuna Salad' },
  { name: 'Steak' },
]
const cheeses = [
  { name: 'American Cheese' },
  { name: 'Cheddar Cheese' },
  { name: 'Swiss Cheese' },
  { name: 'Provolone Cheese' },
  { name: 'Pepperjack Cheese' },
  { name: 'Mozzarella Cheese' },
  { name: 'Feta Cheese' },
]
const condiments = [
  { name: 'Mayonnaise' },
  { name: 'Mustard' },
  { name: 'Honey Mustard' },
  { name: 'Barbecue Sauce' },
  { name: 'Ranch Dressing' },
  { name: 'Light Ranch Dressing' },
  { name: 'Chipotle Southwest Sauce' },
  { name: 'Vinaigrette' },
  { name: 'Italian Dressing' },
  { name: 'Balsamic Vinegar' },
  { name: 'Ketchup' },
  { name: 'Buffalo Sauce' },
  { name: 'Caesar Dressing' },
]
const vegetables = [
  { name: 'Lettuce' },
  { name: 'Tomatoes' },
  { name: 'Cucumbers' },
  { name: 'Red Onions' },
  { name: 'Green Peppers' },
  { name: 'Olives' },
  { name: 'Spinach' },
  { name: 'Pickles' },
  { name: 'Jalapeños' },
  { name: 'Banana Peppers' },
  { name: 'Avocado' },
]
</script>

<style scoped></style>
