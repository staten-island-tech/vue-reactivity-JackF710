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
  'Wheat Bread',
  'White Bread',
  'Italian Bread',
  'Malted Rye',
  'Plain Wrap',
  'Gluten Free Wrap',
  'Multigrain Wrap',
]
const meats = [
  'Oven Roasted Chicken',
  'Sweet Onion Chicken Teriyaki',
  'Grilled Chicken',
  'Meatballs',
  'Roast Beef',
  'Turkey Breast',
  'Turkey Bacon',
  'Salami',
  'Pepperoni',
  'Bacon',
  'Black Forest Ham',
  'Tuna Salad',
  'Steak',
]
const cheeses = [
  'American Cheese',
  'Cheddar Cheese',
  'Swiss Cheese',
  'Provolone Cheese',
  'Pepperjack Cheese',
  'Mozzarella Cheese',
  'Feta Cheese',
]
const condiments = [
  'Mayonnaise',
  'Mustard',
  'Honey Mustard',
  'Barbecue Sauce',
  'Ranch Dressing',
  'Light Ranch Dressing',
  'Chipotle Southwest Sauce',
  'Vinaigrette',
  'Italian Dressing',
  'Balsamic Vinegar',
  'Ketchup',
  'Buffalo Sauce',
  'Caesar Dressing',
]
const vegetables = [
  'Lettuce',
  'Tomatoes',
  'Cucumbers',
  'Red Onions',
  'Green Peppers',
  'Olives (Black or Green)',
  'Spinach',
  'Pickles',
  'Jalapeños',
  'Banana Peppers',
  'Avocado',
]
</script>

<style scoped></style>
